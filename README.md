# anki_style

Basic `box`:
``` html
<div class="box">{{field}}</div>
```
<br>
<br>

Basic `header` box:
``` html
<div class="box header">{{field}}</div>
```
<br>
<br>

Colored `header` box:
``` html
<div class="box header hcolor">{{field}}</div>
<div class="box header hgray">{{field}}</div>
```
This is a purely aesthetic adjustment to the top border color of the `header` class.
<br>
<br>

Basic `conversation` box:
``` html
<div class="box conversation">{{field}}</div>
```
This is used for conversation cards. Fonts are styled smaller and some minor aesthetic adjustments.
<br>
<br>

`question` box:
``` html
<div class="box question">{{field}}</div>
```
This is another purely aesthetic class. A `question` box in this context would be a question/concern about the current card that can be returned to at a later time with a native speaker or teacher.
<br>
<br>

`peek` box:
```html
<div class="box peek">{{field}}</div>
```
This takes any `box` class and makes the inner text invisible until a hover. It makes cards "three-sided." A sentence translation can be revealed on the back template only after someone has hovered over the box. For example, with a listening card, the back of a card can be revealed to confirm what was heard in the target language without revealing the translation.
<br>
<br>

`tag` box:
```html
<div class="box tags">{{field}}</div>
```
Faintly displays the current tags.
<br>
<br>

`pic` box:
```html
<div class="box pic">{{field}}</div>
```
Just some basic image formatting.
<br>
<br>

`hidden`:
```html
<div class="hidden">{{field}}</div>
```
Field contents are not rendered on card. Primarily used in two cases. Hide text that's being fed to AwesomeTTS and hide text being fed to a javascript function.
<br>
<br>


#### Example:
`Note:` Sentence `Card:` Listen
``` html
<!-- Front Template -->
<div class="box header hcolor">Écoute:</div>
{{^Audio}}<tts class="hidden" group="FrenchVoices">{{Phrase}}</tts>{{/Audio}}
{{#Audio}}{{Audio}}{{/Audio}}

<!-- Style -->
@import '_french_style.css';

<!-- Back Template -->
<div class="box header hcolor" id=sentence>{{Phrase}}</div>
{{#Anglais}}<div class="box peek">{{Anglais}}</div>{{/Anglais}}
{{#Notes}}<div class="box" id=notes>{{Notes}}</div>{{/Notes}}
{{#Question!}}<div class="box question">{{Question!}}</div>{{/Question!}}
{{#Tags}}<div class="box tags"># {{Tags}}</div>{{/Tags}}
```

[Google Fonts : Roboto Slab](https://fonts.google.com/specimen/Roboto+Slab)

---
