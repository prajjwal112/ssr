# ssr
server side rendering using angular universal 9

----to add angular universal : ng add @nguniversal/express-engine
----ng run server-side-rendering:prerender  ----- prerenders static routes
dist folder is created in that browser and server folders are created, routes that needs to be prerendered are inside browser

----to prerender any dynamic routes for example that are dependent on id
we need to create routes.txt (name can be anything) and put the dynamic routes that we want to prerender.

ng run server-side-rendering:prerender --routesFile routes.txt

----in case you don't want to create any file :
ng run server-side-rendering:prerender --routes 'todos/1' --routes 'todos/2'

----ng g m home --route home --module app --dry-run  -------- home is the new module getting created, with route home inside app module, 
															dry run is for checking whether it works or not
                              
Why use server-side rendering?
There are three main reasons to create a Universal version of your app.

1-Facilitate web crawlers through search engine optimization (SEO)
2-Improve performance on mobile and low-powered devices
3-Show the first page quickly with a first-contentful paint (FCP)    

Show the first page quickly
Displaying the first page quickly can be critical for user engagement. Pages that load faster perform better, even with changes as small as 100ms. Your app may have to launch faster to engage these users before they decide to do something else.

With Angular Universal, you can generate landing pages for the app that look like the complete app. The pages are pure HTML, and can display even if JavaScript is disabled. The pages don't handle browser events, but they do support navigation through the site using routerLink.

In practice, you'll serve a static version of the landing page to hold the user's attention. At the same time, you'll load the full Angular app behind it. The user perceives near-instant performance from the landing page and gets the full interactive experience after the full app loads.
