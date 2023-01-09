This page explains how you can customize how your [[Introduction to Obsidian Publish|Obsidian Publish]] site looks and feels.

## Static assets

You can customize your site by [[Publish and unpublish notes#Publish notes|publishing]] the following files to your site:

- `publish.css` to add custom CSS
- `publish.js` to add custom JavaScript
- `favicon-32x32.png` to set the favicon

**Notes:**

- Since Obsidian doesn't support CSS or JavaScript files, you need to use another application to create and edit them.
- By default, `publish.css` and `publish.js` don't appear in the file explorer, but you can still publish them from the **Publish changes** dialog.
- To use custom JavaScript with `publish.js`, you need to [[Set up a custom domain]].

For favicons, Obsidian Publish supports the following naming conventions, where `32` is the icon dimensions in pixels:

- `favicon-32.png`
- `favicon-32x32.png`
- `favicon.ico`

We recommend that you provide one or more of the following dimensions:

- `favicon-32x32.png`
- `favicon-128x128.png`
- `favicon-152x152.png`
- `favicon-167x167.png`
- `favicon-180x180.png`
- `favicon-192x192.png`
- `favicon-196x196.png`

## Use a community theme

To use one of the community themes for your site:

1. Open your vault in the default file explorer for your OS.
2. Go to the vault settings folder (default: `.obsidian`).
3. Open the `themes` folder.
4. Copy the CSS file for the theme you want to use for your site.
5. Paste the file into the root folder of your vault.
6. Rename the CSS file to `publish.css`.
7. [[Publish and unpublish notes#Publish notes|Publish]] `publish.css`.

**Notes:**

- If the style doesn't change within a few minutes, you may need to refresh your browser cache.
- You can switch between light and dark mode in the [[Manage sites#View site options|site options]].

## Enable UI features

You can toggle several UI features for your site, such as the graph view or a table of contents.

Browse the available UI features under the **Reading experience** and **Components** sections in the [[Manage sites#View site options|site options]]
