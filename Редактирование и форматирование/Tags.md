---
aliases: 
- How to/Working with tags
---

Tags are keywords or topics that help you quickly find the notes you want.

## Add a tag to a note

To create a tag, enter a hashtag symbol (#) in the editor, followed by a keyword. For example, `#meeting`.

You can also add tags using the `tags` [[Properties|property]]. Tags in YAML should always be formatted as a list:

```yaml
---
tags:
  - recipe
  - cooking
---
```

## Find notes using tags

To find notes using the [[Поиск]] plugin, use the `tag` [[Поиск#Search operators|search operator]] in your search term, for example `tag:#meeting`.

You can also search for tags by clicking on them in your notes.

To find notes using the [[Панель тегов|Панель тегов]] plugin, select **Tags: Show tags** in the [[Палитра команд]], and then select the tag you want to search for.

## Nested tags

Nested tags define tag hierarchies that make it easier to find and filter related tags.

Create nested tags by using forward slashes (`/`) in the tag name, for example  `#inbox/to-read` and `#inbox/processing`.

Both the [[Поиск]] and [[Панель тегов|Панель тегов]] plugins support nested tags.

## Tag format

You can use any of the following characters in your tags:

- Alphabetical letters
- Numbers
- Underscore (`_`)
- Hyphen (`-`)
- Forward slash (`/`) for [[#Nested tags]]

Tags must contain at least one non-numerical character. For example, #1984 isn't a valid tag, but #y1984 is.

Tags can't contain blank spaces. To separate two or more words, you can instead use the following formats:

- #camelCase
- #PascalCase
- #snake_case
- #kebab-case
