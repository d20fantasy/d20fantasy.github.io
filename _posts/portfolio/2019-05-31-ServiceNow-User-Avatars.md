---
layout: post
title: ServiceNow and Dicebear Avatars Integration
img: "assets/img/portfolio/UserAvatars.gif"
tags: [ServiceNow,Integration,App]
---

![Alt Text]({{ page.img | relative_url }})

#### What is it?

The **Avatars** application generates avatars for user records. Say goodbye to boring Initials!<!--endexcerpt-->

> x_snc_avatars.Avatar().get(String sys_id, String sprite_collection);

> x_snc_avatars.Avatar().getRandom(String sys_id);

- sys_id = sys_user.sys_id (Required)
- sprite_collection = force a specific sprite to be returned (Optional)

#### Included in update set

- Script include that allows you generate avatars
- User form UI Action that allows you to generate an avatar for the current user record (Requires the user_admin role). The generated avatar is based on the user's gender and sys_id. Will always produce the same result.
- User form UI Action that allows you to generate a completely random avatar regardless of gender and sys_id. Will always produce a different result.
- Business Rule that will generate an avatar for new user records as they are created.
- System Properties that allow you further customize how it runs, organized into a system property category that will appear as `Avatar Properties` within the `System UI` Application in the navigation menu.

#### Available Sprite Collections (with three random examples)

- male ![male](https://avatars.dicebear.com/v2/male/seed.svg =50x50)
- female 
- identicon 
- bottts 
- avataaars 
- jdenticon 
- gridy 

#### System Properties

- x_snc_avatars.avatars.sprites.default - The default sprite collection to default to if there is no gender provided on the user record.
- x_snc_avatars.avatars.sprites.valid - The sprite collections you want to allow for the randomizer.
- x_snc_avatars.avatars.sprites.use_gender - If you want the sprite generator to check for gender or not.
- x_snc_avatars.avatars.generate_on_insert - If you want the sprite generator to activate for new records
- x_snc_avatars.avatars.generate_on_insert.seed_or_random - If you want new records to be completely random or based on sys_id+gender
- x_snc_avatars.avatars.show_ui_actions - If you want the UI actions to appear on the sys_user form for user_admins.

#### Where to get it

The application is available on [the share website](https://developer.servicenow.com/app.do#!/share/contents/1655773_unique_avatars_for_users?t=PRODUCT_DETAILS).

#### Attribution

- Avatars are provided via API at https://avatars.dicebear.com/
- ServiceNow Integration created by Earl Duque