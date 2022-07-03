# Markdown to Bootstrap Components


List of the markdown code necessary to be converted in Bootstrap components.

Each version of this specification is published as a Release.

Current version: 0.1

# Manifest

* make code the most simple for writers
* avoid unnecessary caracters, especially those hard to type due to key combination on desktop and submenu navigation on mobile: {,},%,[,]
* if possible, create an implementation that deducts the bootstrap component from the markdown organisation itself and from content semantics, rather than from explicit coding
* Markdown ::: Div inclusion should be kept minimalistic


# Known implementations Projects
The known implementation will be published here.

| Language or software | Bootstrap 4 | Bootstrap 5 |
| ----- | ----- | ----- |
| Pandoc Lua | Partial | Mostly |
| Hugo (Node) |  |  |
| Vuepress (Vue) |  |  |
| Machine Learning (TF) | | | 
| Machine Learning (Brain.js) | | | 


# Components

Here is the markdown code to create the various Bootstrap components. Remarks are added for implementation.

----

## JUMBOTRON



* [Jumbotron discussion Page](https://github.com/fxpar/Markdown-to-Bootstrap/wiki/Jumbotron)  :for more explanation about why it works this way


### Markdown

```
::: jumbotron
# Main title of the jumbotron
The first paragraph is always a lead text.

More paragraphs can be added after the horizontal line.
:::
```

### Remarks

**The title CAN be of different level than 1** : mostly jumbotron are meant to be big. But for table of contents, it might be useful to put a header smaller than h1. User choice should be reflected in the output.

**First paragraph after title is "lead"**: only the first paragraph has a "lead" class.

**The horizontal line is not necessayr** : as per definition, jumbotron includes a line after the first paragraph. 
* color of the line border SHOULD follow the color of the text


----

## ALERTS

All the bootstrap color are included:
* primary
* secondary
* info
* warning
* danger
* light
* dark

### Markdown

```
::: info
Here is an information alert
:::
```

### Remarks

**Alert can be included in most other components**


----

## CARDS
See also carddeck

### Markdown

```

::: card

::: header
The card-header can include anything: text, format, buttons, images
:::

# Card can contain titles

And one or more paragraphs
Even links or images

::: footer
This content is in the foot. Formated text can be there.
:::

:::

```

### Remarks

**Header and footer MUST be optional**: they are not required in bootstrap documentation

**Content is considered as card-body**: markdown code doesn't require a ::: body to be included

**Colon number is not relevant**: following pandoc, the number of colons can be increased for readability. 

**Cards can be included in most other components


----

## CAROUSEL

### Markdown






---- 

## ACCORDION

### Markdown

```

::: accordion

# Accordion Item #1
First toggle content

# Accordion Item #2
Second toggle content

# Accordion Item #3
Third toggle content

:::

```

### Remarks

**The level of the first title defines the drawer**: the implementation SHOULD apply the first title inside the carousel div as the title level for all slides
** ::: Slide tag is not necessary**: as per the manifest, it SHOULD NOT be necessary to add other divs to create the accordion
** ::: Slide tag COULD be implemented**: user might want to include same title level inside the drawer. Allowing the use of ::: Slide could be useful.
