# Prose

Prose provides a beatifully simple content authoring environment for [CMS-free websites](http://developmentseed.org/blog/2012/07/27/build-cms-free-websites/). It's a web-based interface for managing content on [GitHub](http://github.com). Use it to create, edit, and delete files, and save your changes directly to GitHub. Host your website on [GitHub Pages](http://pages.github.com) for free, or set up your own [GitHub webhook server](http://developmentseed.org/blog/2013/05/01/introducing-jekyll-hook/).

[Read more about Prose](http://prose.io/#about)

Setup instructions - 
(Thanks to http://www.maxmasnick.com/2012/07/03/prose/)

**Step 1: Gatekeeper**
Prose uses a Node application called Gatekeeper to authenticate with GitHub. I went ahead and set up my own instance of this application on Heroku. This is pretty easy to do:

* Register a new application with GitHub’s API. Set the callback URL to http://prose.dev Note your API id and secret.
* Clone Gatekeeper locally.
* In your local gatekeeper/ folder, run heroku create gatekeeper-yourname.
Then run heroku config:add OAUTH_CLIENT_ID=GITHUB_CLIENT_ID OAUTH_CLIENT_SECRET=GITHUB_CLIENT_SECRET NODE_ENV=production, replacing the client and secret placeholders with your actual IDs.
* Run git push heroku.

**Step 2: Prose**

* Clone Prose locally.
* Edit the prose/oauth.json file to add your github client id under oauth_client_id and gatekeeper-yourname.herokuapp.com for the gatekeeper_url. 
* Add rule to make prose.dev redirect to localhost:8000 to your /etc/hosts file.
* Start a basic python HTTPServer using `python -m SimpleHTTPServer` 
* Prose should be up with oauth setup at http://localhost:8000/




*Prose is developed and maintained by [Development Seed](http://developmentseed.org).*
