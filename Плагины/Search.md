The Search plugin helps you find files in your vault.

By default, you can find Search in the left sidebar (magnifying glass icon). You can also open Search by pressing `Ctrl+Shift+F` (or `Cmd+Shift+F` on macOS).

- **Search selected text**: If you select text in the editor and open Search with the keyboard shortcut, Search shows you the search results for the selected text.
- **Search recent search terms**: Open Search with an empty search term to list recent search terms. Click any of them to use the search term again.

## Search terms

A search term is the word or phrase that you enter in the search field. Learning how to write search terms effectively can help you quickly find what you're looking for, even in large vaults.

Each word in the search term is matched independently within each file. To search for an exact phrase, surround it with quotes, for example `"star wars"`. To search for quoted text within an exact phrase, you can _escape_ the quotes by adding a backslash (`\`) in front of the quote, for example `"they said \"hello\" to each other"`.

You can control whether to return files that contain _all_ the words in your search term, or _any_ of the words:

- `meeting work` returns files that contain both `meeting` and `work`.
- `meeting OR work` returns files that contain either `meeting` or `work`.

You can even combine the two in the same search term.

- `meeting work OR meetup personal` returns files for work meetings and personal meetups.

You can use parentheses to control the priority of each expression.

- `meeting (work OR meetup) personal` returns files that contain `meeting`, `personal`, and either `work` or `meetup`.

To exclude a word from the search results, add a hyphen (`-`) in front of it:

- `meeting -work` returns files that contain `meeting` but not `work`.

> [!tip] Explain search term
> If you need to troubleshoot a complex search term, you can click **Explain search term** in the Search pane for an explanation of your search term.

## Search operators

Search operators enable more fine-grained search queries to filter your results even more.

Some operators even allow you to add a nested search term within parentheses, for example: `task:(call OR email)`.

| Search operator | Description                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `file:`         | Find text in filename.<p/>Example: `file:.jpg` or `file:202209`.                                                                                                                                                     |
| `path:`         | Find text in file path.<p/>Example: `path:"Daily notes/2022-07"`.                                                                                                                                                    |
| `content:`      | Find text in file content.<p/>Example: `content:"happy cat"`.                                                                                                                                                        |
| `match-case:`   | Case-sensitive match.<p/>Example: `match-case:HappyCat`.                                                                                                                                                             |
| `ignore-case:`  | Case-insensitive match.<p/>Example: `ignore-case:ikea`.                                                                                                                                                              |
| `tag:`          | Find tag in file.<p/>Example: `tag:#work`.<p/>**Note**: Since `tag:` ignores matches in code blocks and in non-Markdown content, it's often faster and more accurate than a normal full-text search for `#work`.     |
| `line:`         | Find matches on the same line.<p/>Example: `line:(mix flour)`.                                                                                                                                                       |
| `block:`        | Find matches in the same block.<p/>Example: `block:(dog cat)`.<p/>**Note**: Since `block:` requires Search to parse the Markdown content in every file, it can cause your search term to take longer time to finish. |
| `section:`      | Find matches in the same section (text between two headings).<p/>Example: `block:(dog cat)`.                                                                                                                         |
| `task:`         | Find matches in a [[Format your notes#Task list\|task]] on a block-by-block basis.<p/>Example: `task:call`.                                                                                                          |
| `task-todo:`    | Find matches in an *uncompleted* [[Format your notes#Task list\|task]] on a block-by-block basis.<p/>Example: `task-todo:call`.                                                                                      |
| `task-done:`    | Find matches in a *completed* [[Format your notes#Task list\|task]] on a block-by-block basis.<p/>Example: `task-done:call`.                                                                                         |

## Use regular expressions in search terms

A regular expression is a set of characters that describe a text pattern. To use regular expressions in your search term, surround the expression with forward slashes (`/`).

- `/\d{4}-\d{2}-\d{2}/` matches an ISO 8601 date, such as 2022-01-01.

You can even combine regular expressions with search operators:

- `path:/\d{4}-\d{2}-\d{2}/` returns files with a date in the file path.

For more information on how to write regular expressions, refer to [Regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)

> [!note]
> Regular expressions come in different flavors that may look different from each other. Obsidian uses JavaScript-flavored regular expressions.

## Configure search settings

To configure Search, use the settings at the top of the Search pane:

| Setting                 | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| **Match case**          | Toggles case-sensitive matching.                                            |
| **Explain search term** | Breaks down the search terms and explains it in plain text.                 |
| **Collapse results**    | Toggles whether to show the search context.                                 |
| **Show more context**   | Expands the search result to show more text around the match.               |
| **Change sort order**   | Change the order of the search results.                                     |
| **Copy search results** | Convert and copy the search results as a Markdown list with optional links. |

## Embed search results in a note

To embed search results in a note, add a `query` codeblock:

<pre><code>```query
embed OR search
```</code></pre>

For example:

> [!note]
> [[Introduction to Obsidian Publish|Obsidian Publish]] doesn't support embedded search results. To see the example, open Obsidian Help locally inside Obsidian.

```query
embed OR search
```
