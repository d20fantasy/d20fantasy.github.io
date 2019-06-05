---
layout: post
title: Custom Notifications for non-admins
img: "assets/img/portfolio/Custom Notifications - Result.png"
tags: [ServiceNow,Enhancement]
---

With an idea from our analyst, Robert Weibezahl, I was able to make it so that users with catalog access are now able to update notifications on the fly without having full access to the notifications table<!--endexcerpt-->:

![Resulting notification with substituted variables](/assets/img/portfolio/Custom Notifications - Form.png)

Users can go to a catalog item form (see above) and update the notification that is sent to the user at their own discretion. They are even able to use `variable_name` (wrapped in double curly braces) in the message body and it will automatically insert the value of the catalog item variable of the same name. They can .dot-walk down a level, too!

The final e-mail from the above example looks like this:

![Resulting notification with substituted variables]({{ page.img | relative_url }})

### Structure

1. A catalog admin inputs a message body onto the catalog item itself
2. The catalog item workflow creates an event action that passes the recipients in parameter 1 and the sys_req_item sys_id in parameter 2.
3. The event triggers a notification that sends the message to everyone in event.parm1 and runs the following mail_script for the message body:

```
(function runMailScript(current, template, email, email_action, event) {

	var sc_req_item_gr = new GlideRecord("sc_req_item");
	if(sc_req_item_gr.get(event.parm2)){
		var message_body;
		message_body = sc_req_item_gr.cat_item.u_request_received;
		if (message_body) {
			var regex = /\{\{(.*?)\}\}/g; //every instance of {{variable}}
			var found_variables = message_body.match(regex);
			for (var i in found_variables){
				var variable_name = found_variables[i].replace(/\{|\}/g,""); //remove { and }
				if (variable_name.indexOf('.') != -1){
					var dot_walking = variable_name.split('.'); //if the variable name is an attempt to dot walk
					message_body = message_body.replace(found_variables[i],sc_req_item_gr.variables[dot_walking[0]][dot_walking[1]].getDisplayValue()); //replace variable.subvariable with value
				} else message_body = message_body.replace(found_variables[i],sc_req_item_gr.variables[variable_name].getDisplayValue()); //replace variable with value
			}
			template.print(message_body);
		}
		else template.print("No Message Body Found for this Catalog Item");
	} else template.print("No RITM Found");
})(current, template, email, email_action, event);
```