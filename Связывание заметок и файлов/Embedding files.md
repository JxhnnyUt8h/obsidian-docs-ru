---
aliases: 
- How to/Embed files
---

Learn how you can embed other notes and media into your notes. By embedding files in your notes, you can reuse content across your vault.

To embed a file in your vault, add an exclamation mark (`!`) in front of an [[Internal links|Internal link]]. You can embed files in any of the [[Accepted file formats]].

## Embed a note in another note

To embed a note:

```md
![[Internal links]]
```

You can also embed links to [[Internal links#Link to a heading in a note|headings]] and [[Internal links#Link to a block in a note|blocks]].

```md
![[Internal links#^b15695]]
```

The text below is an example of an embedded block:

![[Internal links#^b15695]]

## Embed an image in a note

To embed an image:

```md
![[Engelbart.jpg]]
```

![[Engelbart.jpg]]

You can change the image dimensions, by adding `|640x480` to the link destination, where 640 is the width and 480 is the height.

```md
![[Engelbart.jpg|100x145]]
```

If you only specify the width, the image scales according to its original aspect ratio. For example, `![[Engelbart.jpg|100]]`.

![[Engelbart.jpg|100]]

## Embed an audio file in a note

To embed an audio file:

```md
![[Excerpt from Mother of All Demos (1968).ogg]]
```

![[Excerpt from Mother of All Demos (1968).ogg]]

## Embed a PDF in a note

To embed a PDF:

```md
![[Document.pdf]]
```

You can also open a specific page in the PDF, by adding `#page=N` to the link destination, where `N` is the number of the page:

```md
![[Document.pdf#page=3]]
```

You can also specify the height in pixels for the embedded PDF viewer, by adding `#height=[number]` to the link. For example:

```md
![[Document.pdf#height=400]]
```

## Embed a list in a note

To embed a list from a different note, first add a [[Internal links#Link to a block in a note|block identifier]] to your list:

```md

- list item 1
- list item 2

^my-list-id
```

Then link to the list using the block identifier:

```md
![[My note#^my-list-id]]
```

## Embed search results 

![[Поиск#Embed search results in a note]]
