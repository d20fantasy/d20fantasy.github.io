---
layout: post
title: 
img: "assets/img/portfolio/Service Portal Favorites 3.PNG"
date: 
tags: [ServiceNow,Service Portal]
---

We thought it would be useful for users to be able to be able to save _any_ page in the Service Portal as a "favorite" page for later access.

I was able to add a button to the header menu:

![New "Add to Favorites" button](/assets/img/portfolio/Service Portal Favorites 1.PNG)

When clicked, a modal window would appear:

!["Add to Favorites" Modal window](/assets/img/portfolio/Service Portal Favorites 2.PNG)

The user would have an option to name the link anything they wanted to or it would otherwise default to the date/time it was saved. Confirming the selection would then save the URL as a favorite.

Specifically, the code that I used to grab the user's current location was:

``` 
uri = gs.action.getGlideURI().toString();
add_fav.setValue('u_url', 'https://INSTANCE.service-now.com/sp/?' + uri.substring(uri.indexOf("api=api") + 8)); 
```

add_fav was the GlideRecord that was saving the favorite entry to a custom table.

![Accessing your Service Portal Favorites]({{ page.img | relative_url }})

The resulting "My Favorites" widget can be placed anywhere or sit as its own page. The favorites were organized further automatically according to the section of the portal you were in.

We also added the ability to add a favorite manually, so you could even add links to the non-portal view of ServiceNow, or even to other websites entirely.