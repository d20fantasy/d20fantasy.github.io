---
layout: post
title: JSON Résumé 
img: "assets/img/portfolio/JSON Resume.png"
date: January, 07 2019
tags: [App,API,ServiceNow]
---

![Screenshot of a REST Get request retrieving an online résumé]({{ page.img | relative_url }})

I created a JSON builder based on [https://jsonresume.org/schema/](https://jsonresume.org/schema/).<!--endexcerpt--> Which is the idea that one of the best ways to present your résumé is through a JSON object since it's standardized and easy for programmers to understand or manipulate en masse.

This ServiceNow app is based on 3 tables: Items, Objects, and Arrays. Records with no parents are the first level of information on the JSON object and the rest are built as children dynamically. To view your object, you can send a GET request to `https://INSTANCE.service-now.com/api/x_snc_json_resume/json_resume` or just navigate to that address, or you can view a prettier version of the object `https://INSTANCE.service-now.com/jsonresume`

The update set can be downloaded on [the share website](https://developer.servicenow.com/app.do#!/share/contents/1655773_create_a_restful_getcompatible_json_object_quickly_in_servicenow?t=PRODUCT_DETAILS).

My current live demo can be found here: [https://hackathon105.service-now.com/jsonresume](https://hackathon105.service-now.com/jsonresume) or send a GET request to `https://hackathon105.service-now.com/api/x_snc_json_resume/json_resume`

<details>
	<summary>Or click here to see the demo-JSON object that is included in the update set</summary>
	
	`{"What is this?":"This is a JSON builder designed from https://jsonresume.org/schema/","phone":"(912) 555-4321","email":"john@gmail.com","summary":"A Summary of John Doe...","website":"http://johndoe.com","picture":"null","name":"John Doe","label":"Programmer","location":{"region":"California","postalCode":"CA 94115","countryCode":"US","address":"2712 Broadway St","city":"San Francisco"},"languages":[{"language":"English","fluency":"Native speaker"}],"work":[{"website":"http://company.com","endDate":"2014-01-01","startDate":"2013-01-01","position":"President","summary":"Description","company":"Company","highlights":["Started the company"]}],"education":[{"endDate":"2013-01-01","area":"Software Development","startDate":"2011-01-01","studyType":"Bachelor","gpa":"4.0","institution":"University","courses":["DB1101 - Basic SQL"]}],"references":[{"reference":"Reference...","name":"Jane Doe"}],"publications":[{"website":"http://publication.com","publisher":"Company","releaseDate":"2014-10-01","summary":"Description...","name":"Publication"}],"awards":[{"date":"2014-11-01","summary":"There is no spoon","title":"Award","awarder":"Company"}],"skills":[{"level":"Master","name":"Web Development","keywords":["HTML","CSS","Javascript"]}],"interests":[{"name":"Wildlife","keywords":["Ferrets","Unicorns"]}],"volunteer":[{"startDate":"2012-01-01","endDate":"2013-01-01","website":"http://organization.com","position":"Volunteer","organization":"Organization","summary":"Description...","highlights":["Awarded 'Volunteer of the Month'"]}],"profiles":[{"network":"Twitter","url":"http://twitter.com/john","username":"John"}]}`
</details>