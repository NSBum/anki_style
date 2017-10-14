# anki_style

A live version of anki_style can be seen here: https://se110785.github.io/anki_style/

Each of these boxes you see here are part of a standardized style sheet I've developed over the past year or so while using Anki. It by no means is an exhaustive set of classes for all situations but it covers the more basic things when learning a language. Namely reviewing: vocabulary, sentences, and conversations. Most of these classes, if not all, can also be used with any type of card, it's really not limited to languages or any topic.

The motivation behind this was that I was looking for a way to flexibly format and re-format my cards. Removing almost all HTML and CSS from Anki ensures that I can change/edit/tweak the color palette or overall theme without having to sift through thousands of cards.

`box`:
```html
<div class="box">{{field}}</div>
```
![as_0000_box1](images/as_0000_box1.png)
![as_0001_box2](images/as_0001_box2.png)
![as_0002_box3](images/as_0002_box3.png)

<br>


`question` box:
``` html
<div class="box question">{{field}}</div>
```
![as_0003_box-question](images/as_0003_box-question.png)

<br>


`peek` box:

```html
<div class="box peek">{{field}}</div>
```
This takes any `box` class and makes the inner text invisible until a hover. It makes cards "three-sided." A sentence translation can be revealed on the back template only after someone has hovered over the box. For example, with a listening card, the back of a card can be revealed to confirm what was heard in the target language without revealing the translation.

![as_0007_peek](images/as_0007_peek.png)
![as_0008_revealed1](images/as_0008_revealed1.png)
![as_0009_revealed2](images/as_0009_revealed2.png)
![as_0010_revealed3](images/as_0010_revealed3.png)

<br>


`header` box:
``` html
<div class="box header">{{field}}</div>
```
![as_0004_box-header](images/as_0004_box-header.png)

<br>


`header` box colored:
``` html
<div class="box header hcolor">{{field}}</div>
<div class="box header hgray">{{field}}</div>
```
This is a purely aesthetic adjustment to the top border color of the `header` class.

![as_0005_box-header-hcolor](images/as_0005_box-header-hcolor.png)
![as_0006_box-header-hgray](images/as_0006_box-header-hgray.png)

<br>


`conversation` box:
``` html
<div class="box conversation">{{field}}</div>
```
This is used for conversation cards. Fonts are styled smaller and some minor aesthetic adjustments.

![as_0011_conversation](images/as_0011_conversation.png)

<br>


`tag` box:
```html
<div class="box tags"># {{field}}</div>
```
Faintly displays the current tags. Note: Actual style does not have outline.

![as_0012_tag](images/as_0012_tag.png)

<br>


`pic` box:
```html
<div class="box pic">{{field}}</div>
```
<br>


`hidden`:
Field contents are not rendered on card. Primarily used in two cases. Hide text that's being fed to AwesomeTTS and hide text being fed to a javascript function.
```html
<div class="hidden">{{field}}</div>
```
<br>


## Example:
`Note:` Sentence `Card:` Listen

```html
<!-- Front Template -->
<div class="box header hcolor">Écoute:</div>
{{^Audio}}<tts class="hidden" group="FrenchVoices">{{Phrase}}</tts>{{/Audio}}
{{#Audio}}{{Audio}}{{/Audio}}

<!-- Style -->
@import '_anki_style.css';

<!-- Back Template -->
<div class="box header hcolor">{{Phrase}}</div>
{{#Anglais}}<div class="box peek">{{Anglais}}</div>{{/Anglais}}
{{#Notes}}<div class="box">{{Notes}}</div>{{/Notes}}
{{#Question!}}<div class="box question">{{Question!}}</div>{{/Question!}}
{{#Tags}}<div class="box tags"># {{Tags}}</div>{{/Tags}}
```

[Google Fonts : Roboto Slab](https://fonts.google.com/specimen/Roboto+Slab)

---

## Installation