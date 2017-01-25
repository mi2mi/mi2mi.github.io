---
layout: post
title: Angular Deep Linking
category: AngularJS
tags: [angular, deep linking]
directUrl: http://www.divami.com/blog/deep-linking-angular/
---

Angular by default provides deep linking using '#'. These urls may not inexed in search engines due to '#'. We can get rid of it using [Read more...](http://www.divami.com/blog/deep-linking-angular/)


<!--



Implementing deep linking in AngularJS applications.

Deep Linking
------------
Deep linking is the usage of the URL, which will take to specific page (or content) directly without traversing application from home page [1]. It helps in easily searchable and indexed in search engines like Google, Yahoo & etc.

**Examples for deep linking urls**:
http://www.divami.com/blog/angular-deep-linking/
https://www.linkedin.com/groups/4314060/profile
https://www.facebook.com/pages/JavaScript/113124472034820
 
 
Deep Linking in Angular
-----------------------
**With '#'**:
Angular by default supports deep linking using **'#'**.

**Ex**: https://www.deeplinking.com#/deep/linking

It has following drawbacks

 - Search engines (SEO) won't recognise the url after '#', so the page full path will not indexed.
 - Google analytics also will not  capture the url after '#', so we may not get results as we want.
 - Readability will decrease


**Removing '#'**: 
 We have to do following to get rid of '#' in url.
 
1. **Enable html5Mode**: We have to enable this in application config file.

	> `$locationProvider.html5Mode(true).hashPrefix('!');`

	Some browsers don't support html5Mode, for that we need to add hashPrefix('!').

2. **Loading files**: Generally in header we include files as follows

	> `<script src="vendor/angular.js"></script>` 

	After enabling html5Mode, files may not load correctly. To fix this we have to set

    > `<base `**`href="/"`**` />`
	`or`
    `<script `**`src="/vendor/angular.js"`**`></script>`

	**Note**: If you mention href value as **'/'**, it will refer to server url. If you want to point to other domain path, which can set to href (Ex: In localhost it will not work with **'/'**, so we need to mention it as `<base href="http://localhost/appFolder/" />`

3.  **Enabling Redirection**: Reload & Refresh will not work after **html5Mode** is enabled, because browser will look for folders and it leads to `404 Not Found`. To get it worked we need to redirect to `index.html` file, for that we have to add the following in `.htaccess` file (or in sever configuration)[2]:

	>     RewriteEngine on
	>     
	>     # Don't rewrite files or directories
	>     RewriteCond %{REQUEST_FILENAME} -f [OR]
	>     RewriteCond %{REQUEST_FILENAME} -d
	>     RewriteRule ^ - [L]
	>      
	>      # Rewrite everything else to index.html to allow html5 state links
	>     RewriteRule ^ index.html [L]

	**Note**: If you are using `debug.html` for development and `index.html` for production, then you have to redirect to debug.html instead of index.html for development purpose.

4. You need to remove **'#'s** before urls if you use any. We use it when we use  $routeProvider as follows:

	> `<a href="#deep/linking">Deep Linking</a>`

**References**:

1. https://en.wikipedia.org/wiki/Deep_linking
2. https://github.com/angular-ui/ui-router/wiki/Frequently-Asked-Questions#how-to-configure-your-server-to-work-with-html5mode-->
