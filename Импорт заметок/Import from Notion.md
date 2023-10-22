---
permalink: import/notion
---
Obsidian allows you to easily migrate your notes from Notion using the [[Импортер|Importer plugin]].

## Export your data from Notion

Obsidian uses Notion's HTML export format. You can find Notions's instructions on how to export your entire workspace [on Notion's website](https://www.notion.so/help/export-your-content). Note that you must be a workspace admin to see this option.

1. Go to **Settings & members** at the top of your left-hand sidebar.
2. Select **Settings** in the sidebar of that window.
3. Scroll down and click the **Export all workspace content** button.
4. Under **Export format** select **HTML**.
5. You will receive a `.zip` file via email or directly in the browser.

![[notion-export.png]]

## Import your Notion data into Obsidian

You will need the official Obsidian [[Импортер]] plugin, which you can [install here](obsidian://show-plugin?id=obsidian-importer).

1. Open **Settings**.
2. Go to **Community Plugins** and [install Importer](obsidian://show-plugin?id=obsidian-importer).
3. Enable the Importer plugin.
4. Open the **Importer** plugin using the command palette or ribbon icon.
5. Under **File format** select **Notion (.zip)**
6. Choose the `.zip` file with Notion files you want to import. *It's recommended to import all your Notion at once so internal links can be reconciled correctly.*
7. Optionally, select a folder for the import Your Notion pages and databases will be nested inside this folder.
8. Click **Import** and wait until import is complete
9. You're done!