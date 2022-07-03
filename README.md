# Markdown to Bootstrap Components


List of the markdown code necessary to be converted in Bootstrap components.

# Known implementations
The known implementation will be published here.

| Language or software | Bootstrap 4 | Bootstrap 5 |
| ----- | ----- | ----- |
| Pandoc Lua | Partial | Mostly |
| Hugo (Node) |  |  |


## Components

Here is the markdown code to create the various Bootstrap components. Remarks are added for implementation.

----

### Jumbotron



* [Jumbotron discussion Page](https://github.com/fxpar/Markdown-to-Bootstrap/wiki/Jumbotron)  :for more explanation about why it works this way


#### Markdown

```
::: jumbotron
# Main title of the jumbotron
The first paragraph is always a lead text.

More paragraphs can be added after the horizontal line.
:::
```

#### Remarks

**The title CAN be of different level than 1** : mostly jumbotron are meant to be big. But for table of contents, it might be useful to put a header smaller than h1. User choice should be reflected in the output.

**First paragraph after title is LEAD**: only the first paragraph has a "lead" class.

**The horizontal line is not necessayr** : as per definition, jumbotron includes a line after the first paragraph. 
* color of the line border SHOULD follow the color of the text



