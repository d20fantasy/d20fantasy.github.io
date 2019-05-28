---
layout: post
title: Bad Comment Link Builder
img: "assets/img/portfolio/BadCommentLinkBuilder.gif"
date: September, 27 2018
tags: [QoL,ServiceNow]
---

![image]({{ page.img | relative_url }})

### The problem

Whenever someone sends an e-mail into incident that has PII, PCI, Ferpa, or Hippa violations, we have to remove the comment. Instead of deleting the whole incident, we prefer to locate all the instances of the bad comment and redact<!--endexcerpt--> just the inappropriate content so that the incident as a whole remains in tact. Looking for all the instances of it is straight forward enough (just follow this HI article) but it's time consuming going through all those tables and constructing the URLs manually.

### A shortcut

We made a link builder for finding these comments. See it here:

[Bad Comment Link Builder](https://ucdavisit.service-now.com/servicehub?id=bad_comment_link_builder)

All you have to do is provide your instance name and the sys_id of the incident and it will construct the URLs you need as an admin to go find the comments you want to edit (don't forget to rebuild the history line on the history table).

It's a straight forward widget and has zero server calls. You can use it yourself or even construct the widget on your own instance if you rather have it there or change the default value.

The code is below:

HTML:

    <div class="widget">
      <div>
        <form class="form-horizontal">
          <div class="form-group">
            <label class="col-xs-12 col-md-3 control-label">
              <span class="label-text">Instance</span>
            </label>
            <div class="col-xs-12 col-md-9 form-field input_controls">
              <input value="ucdavisit" class="form-control" ng-model="c.data.instance" ng-change="updateLinks()"/>
            </div>
          </div>
          <div class="form-group">
            <label class="col-xs-12 col-md-3 control-label">
              <span class="label-text">Incident sys_id</span>
            </label>
            <div class="col-xs-12 col-md-9 form-field input_controls">
              <input value="" class="form-control" ng-model="c.data.sys_id" ng-change="updateLinks()" />
              <div class="warn" ng-if="data.bad_id_length == true">
                Must be 32 characters
              </div>
            </div>
          </div>
        </form>
      </div>
      <div class="form-horizontal" ng-if="data.journal_link != ''">
        <div class="form-group">
          <label class="col-xs-12 col-md-3 control-label">
            <span class="label-text">Links</span>
          </label>
          <div class="col-xs-12 col-md-9 form-field">
            <div>
              <a href="{{data.journal_link}}" target="_blank">Journal Field List</a>
            </div>
            <div>
              <a href="{{data.audit_link}}" target="_blank">Audit List</a>
            </div>
            <div>
              <a href="{{data.history_link}}" target="_blank">History Set</a>
            </div>
            <div>
              <a href="{{data.email_link}}" target="_blank">Email List</a>
            </div>
          </div>
        </div>
      </div>
    </div>

CSS: 

    .widget {
      background-color: white;
      border: 25px solid white;
      border-radius: 5px;
      padding-left: 30px;
      padding-right: 30px;
      margin: 25px;
      margin-bottom: 20px;
    }

    .warn {
      color: red;
    }

Client: 

    function($scope) {
    	/* widget controller */
    	var c = this;
    	var link1 = 'https://';
    	var link2 = '.service-now.com/';
    	var link_journal = 'sys_journal_field_list.do?sysparm_query=element_id=';
    	var link_audit = 'sys_audit_list.do?sysparm_query=documentkey=';
    	var link_history = 'sys_history_set_list.do?sysparm_query=id=';
    	var link_email = 'sys_email_list.do?sysparm_query=instance=';

    	$scope.updateLinks = function() {
    		if (c.data.sys_id && c.data.instance){
    			if (c.data.sys_id.length != 32) {
    				c.data.bad_id_length = true;
    				c.data.journal_link = '';
    				c.data.audit_link = '';
    				c.data.history_link = '';
    				c.data.email_link = '';
    			} else {
    				c.data.bad_id_length = false;
    				c.data.journal_link = link1 + c.data.instance + link2 + link_journal + c.data.sys_id;
    				c.data.audit_link = link1 + c.data.instance + link2 + link_audit + c.data.sys_id;
    				c.data.history_link = link1 + c.data.instance + link2 + link_history + c.data.sys_id;
    				c.data.email_link = link1 + c.data.instance + link2 + link_email + c.data.sys_id;
    			}
    		} else {
    			c.data.bad_id_length = false;
    			c.data.journal_link = '';
    			c.data.audit_link = '';
    			c.data.history_link = '';
    			c.data.email_link = '';
    		}
    	}
    }
    Server: 

    (function() {
    	/* populate the 'data' object */
    	/* e.g., data.table = $sp.getValue('table'); */
    	data.instance = 'ucdavisit'; //default
    	data.journal_link = '';
    	data.audit_link = '';
    	data.history_link = '';
    	data.email_link = '';
    	data.bad_id_length = false;
    })();