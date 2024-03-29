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
| [Pandoc Lua](https://github.com/fxpar/markdown-to-bootstrap-pandoc-lua-filter) | Partial | Mostly |
| Hugo (Node) |  |  |
| Vuepress (Vue) |  |  |
| Machine Learning (TF) | | | 
| Machine Learning (Brain.js) | | | 
| Moosh (Moodle) | | |


# Technicalities


## Attributes

Bootstrap customization relies mainly on css classes added to html. 

**Attributes MUST be passed from markdown to the component** through a common syntax. 

(see Jumbotron for examples)



## Overrides

Implementation should provide a serie of overrides for the default values.

**Overrides MUST be available in the YAML Front Matter** of the markdown document.

```
---
links-to-button: false
video-to-embeds: false
tabs-pills: true
---

```


# Components

Below is the markdown code to create the various Bootstrap components. 

----

## JUMBOTRON



* [Check an exemple:](https://fxpar.github.io/markdown-to-bootstrap/index.html#sectionJumbotron)  

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

**The horizontal line is not necessary** : as per definition, jumbotron includes a line after the first paragraph. 
* color of the line border SHOULD follow the color of the text

**Attributes MUST be passed**: background color, text color especially 
must be passed through the following attribute syntax


```
::: jumbotron {.bg-success .text-white}
# Title of a colored jumbotron
Lead text of a colored jumbotron.

Description after a horizontal line of a colored jumbotron.
:::

```


----

## ALERTS

* [Check an exemple:](https://fxpar.github.io/markdown-to-bootstrap/index.html#sectionAlerts)  

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

* [Check an exemple:](https://fxpar.github.io/markdown-to-bootstrap/index.html#sectionCards)  

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

**Cards can be included in most other components**

**Images inside a card SHOULD be card-image**: add the card-img and card-fluid classes by default




----

## CAROUSEL

* [Check an exemple:](https://fxpar.github.io/markdown-to-bootstrap/index.html#sectionCarousel)  

### Markdown

```
::: carousel 

# First slide label
Some representative placeholder content for the first slide.

# Second slide label
Some representative placeholder content for the second slide.

# Third slide label
Some representative placeholder content for the third slide.

:::

```

### Remarks

**Carousel id SHOULD NOT be required**: although it might be useful for linking, an automatic id should be applied to the carousel

**Multiple carousel MUST be allowed on a same page**: this reinforce the necessity of an automatic id system

**Level of first title defines the slides**: depending on document structure, user might want to start a carousel from title level 1, 2, 3...

** ::: Slide tag is not necessary**: as per the manifest, it SHOULD NOT be necessary to add other divs to create the accordion

** ::: Slide tag COULD be implemented**: user might want to include same title level inside the slide. Allowing the use of ::: Slide could be useful.



---- 

## ACCORDION

* [Check an exemple:](https://fxpar.github.io/markdown-to-bootstrap/index.html#sectionAccordion)  


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

**The level of the first title defines the drawer**: the implementation SHOULD apply the first title inside the carousel div as the title level for all drawers

**::: Drawer tag is not necessary**: as per the manifest, it SHOULD NOT be necessary to add other divs to create the accordion

**::: Drawer tag COULD be implemented**: user might want to include same title level inside the drawer. Allowing the use of ::: Drawer could be useful.

**Multiple accordions MUST be possible on page**: automatic id is therefore expected in implementation

**Discussion is opened for a short version ::: acc**: for now only the official ::: accordion tag is considered


----

## TABS

* [Check an exemple:](https://fxpar.github.io/markdown-to-bootstrap/index.html#sectionTabs)  

### Markdown

```

::: tabs

# First Tab Link
## Subtitle of the first tab
Content of the first tab

# Second tab Link
## Subtitle for the second tab
Content of the second tab

# Third tab link
## Subtitle for the third tab
Content of the third tab

:::

```

### Remarks

** :::Tabs is singular**: the ::: accordion tag is plural with an "s" at the end (as opposed to most of the other tags). 


---- 

## BUTTONS

* [Check an exemple:](https://fxpar.github.io/markdown-to-bootstrap/index.html#sectionButtons)  

**Links SHOULD turned into buttons**: this is the default conversion behaviour.


---- 

## Embeds

**Some media links should be turned into embeds**: conversion should be simplified for writers

Exemple: youtube syntaxt SHOULD be converted from watch url to embed url automatically