Obsidian Publish™ is a paid hosting service for your notes.

For instructions on how to publish your notes from within the Obsidian app, refer to the [[Publish|Publish plugin]].

### Privacy

You have total control over what to publish via the [[Publish|Publish plugin]] - either your entire vault or just selected notes within your vault. As for any notes you choose **not** to publish, you can be confident that those notes remain completely private, and Obsidian Publish has no knowledge of them.

### Backing up

Please note that Obsidian Publish is not to be used as a backup for your content. Make sure you always have a personal backup copy of your site using your preferred backup method. Our efforts on Obsidian Publish will be more focused on functionality, ease of use, and site availability.

### Demo

There's a good chance that you're already viewing this article on our official site powered by Obsidian Publish.

If not, you can visit it here: https://publish.obsidian.md/help.

### What's included

The Obsidian Publish service lets you create your site directly from within the Obsidian app by choosing the notes you want to publish.

To customize your site, you can choose between light and dark mode, and also toggle between readable line length and full page length.

There are several components which can be turned on or off from the [[Publish|Publish plugin]]. Changes to these options will be reflected on your published site once the cache clears, typically within 5 minutes.

##### Navigation

Enabling this option adds a navigation sidebar displaying all published pages and the folders that contain them. Viewers will see the current open note highlighted, and can click on any other note to navigate.

##### Search bar

Adds a search bar to the navigation pane (requires navigation to be enabled). This bar can be used to search for pages and headings within pages. It does not currently search through the full text content of the site.

##### Graph view

Displays a local graph of the page currently open. This uses the same rendering engine as the [[Graph view]] plugin in Obsidian.

##### Table of contents

Displays a table of contents for the page currently open. The list is generated from headings within the page, similar to the [[Outline]] plugin. Viewers navigating the note will see the corresponding heading highlighted as they scroll, and can click on another heading to immediately navigate to it.

##### Backlinks

Displays a section at the end of each page called "Linked to this page", containing backlinks from other pages. If there are no backlinks, the section will not be displayed.

##### Tags

When the reader clicks on a tag, they can see a list of other pages that includes the same tag.

##### Hover preview

When hovering over links, their content is displayed within a popup box. This works similarly to the [[Page preview]] plugin in Obsidian.

##### Custom CSS

To customize the styling of your site, you can upload a `publish.css`. This file must be stored in the root folder of your site. You can use your existing theme and add some extra tweaks for publish in `publish.css`.

##### Favicon

To change the favicon of your site, you can upload `png` icons of any size in the format of `favicon-32.png` or `favicon-32x32.png`. You can also upload the file `favicon.ico`. These files can be stored in any folder. The current recommendation (as of 2020) is to provide sizes `32×32`, `128x128`, `152×152`, `167x167`, `180x180`, `192x192`, and `196x196`.

##### Custom JS

If you wish to execute your own JavaScript code to change the visitor experience, or add various integrations like Discus!, Discourse, etc. you can do so by uploading `publish.js` inside the root of your vault. Note that these scripts will only run for visitors to your custom domain.

##### Disallow search engine indexing

This option adds a meta noindex tag to all your pages so search engines like Google does not index your site. Note that search engines won't be able to index your site anyway if it's password protected.

##### Google Analytics

If you wish to setup Google Analytics for your site, first make sure your local laws and regulations allows. Then, you just need to put the tracking code, in the form of `UA-XXXXX-Y` into the text box and your site will automatically track page views. Note that Google Analytics is only available to visitors from your custom domain.

### Custom domain

You can setup a custom domain or subdomain for your Obsidian Publish site. Currently, we don't yet have a way to provision SSL certificate on your behalf, so you need to resort to either an SSL-enabled server of your own, or to setup your site on CloudFlare, which provides SSL for free.

You can also setup Obsidian Publish as a sub-URL of a site you own. For example, `https://my-site.com/my-notes/`. To achieve this, you must host your own server and proxy all requests to our server at `https://publish.obsidian.md/`.

Continue reading for setup details.

#### CloudFlare setup

The easiest way to setup a custom domain or subdomain is by making an account with CloudFlare and letting CloudFlare manage your domain. This allows you to add SSL to your site for free, as well as ensure your site is fast wherever in the world it's accessed from.

You'll only need to add a CNAME record to your domain or subdomain, with the value being `publish-main.obsidian.md`. Then, head to the SSL/TLS configuration and set the SSL/TLS encryption mode to `Full`. This will configure the SSL/TLS certificate automatically.

Once you are done with configuring CloudFlare, you can head to your site options in Obsidian, and set the URL to your domain or subdomain. This allows our server to associate the domain to your site.

Troubleshooting: If your custom domain setup ends up in a redirect loop, it's likely that the encryption mode in CloudFlare to `Flexible` instead of `Full`.

If you wish to configure both `my-site.com` and `www.my-site.com` to Obsidian Publish, you will need to create a [Page Rule](https://support.cloudflare.com/hc/en-us/articles/200172336-Creating-Page-Rules) as follows:
- URL match: `www.my-site.com/*`
- Foward URL - 301 Permanent Redirect
- Redirect URL: `https://my-site.com/$1`

Once you create the page rule, you should also create a CNAME record for `www.my-site.com` just like you created for `my-site.com`

#### Proxy/redirect setup

If you wish to host your own web server and setup your own SSL encryption, you can choose this option. If you are already hosting a website under your domain or subdomain, you can also use this option and setup your website to load your Obsidian Publish site under a specific URL path, instead of hosting the full site.

Simply proxy all requests under that URL path to `https://publish.obsidian.md/serve?url=my-domain.com/my-subpath/...` and configure the site options in Obsidian to the same URL path.

For example, in NGINX, you can set it up as:
```nginx
location /my-notes {
  proxy_pass https://publish.obsidian.md/serve?url=my-domain.com/my-notes/;
  proxy_ssl_server_name on;
}
```

In Apache `.htaccess`, you can set it up as:
```htaccess
RewriteEngine  on
RewriteRule    "^my-notes/(.*)$"  "https://publish.obsidian.md/serve?url=my-domain.com/my-notes/$1"  [L,P]
```

If you're using Netlify, you can set it up as:
```
[[redirects]]
  from = "https://my-domain.com/my-notes/*"
  to = "https://publish.obsidian.md/serve?url=my-domain.com/my-notes/:splat"
  status = 200
  force = true
```

#### Custom domain post-setup issues

Once you setup your custom domain, if you've visited your site from your previous `https://publish.obsidian.md/slug` link, you may have to clear your browser cache for certain things (like fonts, graphs, or password access) to work properly. This is due to the cross-domain security restrictions that are imposed by modern browsers. The good news is that readers of your site should never run into issue this if you only let visitors use your custom domain.

#### Redirect old site to custom domain

If you'd like to redirect your visitors from the old `publish.obsidian.md` site to your new custom domain, there is an option you can enable in the custom domain settings page which will do just that.

### Coming up

Obsidian Publish is still in its early days. Here are some features we plan to add:

- Full custom domain support (with SSL certificate provisioning).
- Full text search.
- More built-in themes.

Please let us know if you have any Obsidian Publish feature requests by submitting a [forum request here](https://forum.obsidian.md/).

### Pricing

For the pricing of Obsidian Publish, please visit [our pricing page](https://obsidian.md/pricing).

### Technical details

Obsidian Publish uses Cloudflare as the CDN (content delivery network) to distribute your site across the globe for a faster access. This involves caching copies of the files of your site on some of the 200+ data centers to ensure the lowest latency for your readers and the site remain speedy and loads fast even if your viewer lives far away from our primary servers.

However, this does mean that when you change site settings, publish new content, or unpublish content, visitors might not see the latest version for a short while. Currently, our cache is configured to persist for an hour before it has to be "re-validated" to ensure the content hasn't changed.

If you've just published items but you are still seeing an older version, you can typically perform a "hard refresh" by holding the reload button and choosing "Hard reload" in the dropdown menu. Failing that, you can try clearing the browser cache or disabling cache using the developer tools in the network tab.

---

### Related

Refer to the [[Publish|Publish plugin]] for details on publishing your notes. 
