---
layout: markdeep
permalink: /about/index.html
title: About the Theme
description: Balzac is a new, fluid & responsive theme for Jekyll (and AnchorCMS). It's gloriously beautiful and suited to long form. Built on a SCSS foundation, it's organized and awesome.
tags: [about]
image:
  feature: soft-trees.jpg
---
# ATX Headers
In addition to the underlined headers, you can also use ATX-style
headers, with multiple # signs:

## H2
### H3
#### H4
##### H5
###### H6
Although: do you really need six levels of subsection nesting?!

You can also create unnumbered sections that will not appear in the
table of contents using parentheses around the pound signs:

(##) Unnumbered H2


Multiple Columns
========================================================================
<div style="columns:2;-webkit-columns:2;-moz-columns:2;column-gap:3em;-webkit-column-gap:3em;-moz-column-gap:3em">
You can use the CSS
[columns](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Columns/Using_multi-column_layouts)
style to make an HTML multicolumn block. Then, just use regular Markdeep within it and the
browser will automatically apply your multicolumn layout. 

Browsers are even smart enough to break the columns correctly when
printing to PDF or to a printer. However, for a long document,
multiple columns don't work well when displayed on screen. That's
because there are no discrete "pages" on screen to break columns. So,
the browser will make each column as long as the entire document,
which is probably not what you want.

So, multi-column only works well if you know that you have very short
sections (as in this example), or if you were planning on printing to
separate pages when done.
</div>


Custom Formatting
=========================================================================

Manual
-------------------------------------------------------------------------

Markdeep uses CSS for styling. That means you can embed a style sheet
to override anything thatn you don't like about the built-in styling.
For example, if you don't want section numbering, just use:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
<style>h1:before, h2:before { content: none; }</style>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Markdeep uses Markdown's syntax, even where I disagree with the
choices.  But you aren't stuck with that. Do you wish that Markdown
had specified single-asterisk for `*bold*`? You can have
that:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
<style>em.asterisk { font-style: normal; font-weight: bold; }</style>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Each of the list bullets (`+`, `-`, `*`) has its own CSS class. You
can use this, for example, to make `+` entries bold and `-` ones
use a circle:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
<style>
  li.plus { font-weight: bold; } 
  li.minus { list-style-type: circle;}
</style>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Style Sheets
------------------------------------------------------------------------

### Latex Article

To match the default Latex article formatting, insert the following anywhere in your document:

<pre class="listing tilde"><<span>link</span> rel="stylesheet" href="https://casual-effects.com/markdeep/latest/latex.css?">
</pre>

### Dark 

For an aggressively-stylized document with a black background, insert the following anywhere in
your document:

<pre class="listing tilde"><<span>link</span> rel="stylesheet" href="https://casual-effects.com/markdeep/latest/dark.css?">
</pre>

### API Documentation

To use the API documentation template, insert the following anywhere in
your document:

<pre class="listing tilde"><<span>link</span> rel="stylesheet" href="https://casual-effects.com/markdeep/latest/apidoc.css?">
</pre>

### Presentation Slides

To create presentation slides as a PDF, insert the following into
your document, using first-level headers for sections and second-level
headers for slides:

<pre class="listing tilde"><<span>link</span> rel="stylesheet" href="https://casual-effects.com/markdeep/latest/slides.css?">
</pre>

Then, print the document to PDF.


Paragraph Numbering
--------------------------------------------------

Academic article or book proofs often have line numbers so that reviewers and editors can refer
to specific passages. This doesn't make sense for a document in a browser because line breaks
change based on the reader's screen size. 

You can add _paragraph_ numbers to your Markdeep document by including the following HTML at
the bottom of your document. You can remove the `<style>` tag and place the code in a CSS file
as well.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ html
<style>
p::before {
  content: "¶ " counter(paragraph);
  counter-increment: paragraph;
  margin-left: -50px;
  width: 50px;
  height: 0px;
  overflow: visible;
  font-size: 70%;
  display: block;
  color: #666;
}
</style>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Localization
===================================================

There are two ways to localize the keywords such as Table, Diagram,
Monday, etc., from English to your favorite language. 

The first is to
put a meta tag with a
[`lang`](http://www.iana.org/assignments/language-subtag-registry/language-subtag-registry)
attribute in the document, such as <`meta lang="ru"
charset="utf-8"`>. If your favorite language isn't supported by
Markdeep, just e-mail me a Javascript snippet with the appropriate
translations and I'll add it (see the source code for examples).

The second method is to manually set the `markdeepOptions.lang` field
before you include the script in your document.


Unicode (in UTF-8 encoding)
===================================================

To support Unicode input, you must add <`meta charset="utf-8"`> to
the *top* of your document (in the first 512 bytes).

- Asian characters 林花謝了春紅 太匆匆, 無奈朝來寒雨 晚來風 胭脂淚 留人醉 幾時重, 自是人生長恨 水長東
- Asian punctuation:　、。！，：
- Matching pairs «»‹›“”‘’〖〗【】「」『』〈〉《》〔〕
- Greek ΑΒΓΔ ΕΖΗΘ ΙΚΛΜ ΝΞΟΠ ΡΣΤΥ ΦΧΨΩ αβγδ εζηθ ικλμ νξοπ ρςτυ φχψω
- Currency  ¤ $ ¢ € ₠ £ ¥
- Common symbols © ® ™ ² ³ § ¶ † ‡ ※
- Bullets •◦ ‣ ✓ ●■◆ ○□◇ ★☆ ♠♣♥♦ ♤♧♡♢
- Phonetic ᴁ ᴂ ᴈ
- Music ♩♪♫♬♭♮♯
- Punctuation “” ‘’ ¿¡ ¶§ª - ‐ ‑ ‒ – — ― …
- Accents àáâãäåæç èéêë ìíîï ðñòóôõö øùúûüýþÿ ÀÁÂÃÄÅ Ç ÈÉÊË ÌÍÎÏ ÐÑ ÒÓÔÕÖ ØÙÚÛÜÝÞß 
- Math ° ⌈⌉ ⌊⌋ ∏ ∑ ∫ ×÷ ⊕ ⊖ ⊗ ⊘ ⊙ ⊚ ⊛ ∙ ∘ ′ ″ ‴ ∼ ∂ √ ≔ × ⁱ ⁰ ¹ ² ³ ₀ ₁ ₂ π ∞ ± ∎
- Logic & Set Theory ¬∧∨∃⊦∵∴∅∈∉⊂⊃⊆⊇⊄⋂⋃
- Relations ≠≤≥≮≯≫≪≈≡
- Sets ℕℤℚℝℂ
- Arrows ←→↑↓ ↔ ↖↗↙↘  ⇐⇒⇑⇓ ⇔⇗  ⇦⇨⇧⇩ ↞↠↟↡ ↺↻  ☞☜☝☟
- Computing ⌘ ⌥ ‸ ⇧ ⌤ ↑ ↓ → ← ⇞ ⇟ ↖ ↘ ⌫ ⌦ ⎋⏏ ↶↷ ◀▶▲▼ ◁▷△▽ ⇄ ⇤⇥ ↹ ↵↩⏎ ⌧ ⌨ ␣ ⌶ ⎗⎘⎙⎚ ⌚⌛ ✂✄ ✉✍
- Digits ➀➁➂➃➄➅➆➇➈➉
- Religious and cultural symbols ✝✚✡☥⎈☭☪☮☺☹☯☰☱☲☳☴☵☶☷
- Dingbats ❦☠☢☣☤♲♳⌬♨♿ ☉☼☾☽ ♀♂ ♔♕♖ ♗♘♙ ♚♛ ♜♝♞♟


Gravizo Support
===================================================

Markdeep diagrams have no dependency on third parties or the network 
(you can store the `markdeep.min.js` file locally on your machine!)
and look the same in your document as on screen in the final document.

If you need the full power of DOT/GraphViz automated layout graphs and
can accept a network and third party dependency, you can embed
[Gravizo](http://g.gravizo.com/) within a Markdeep document using either
direct Markdeep image syntax or an embedded HTML `img` tag:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
<img src="http://g.gravizo.com/svg?digraph G { A -> B -> C; A -> C; }">
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<img src="http://g.gravizo.com/svg?digraph G { A -> B -> C; A -> C; }">

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
![](http://g.gravizo.com/svg?digraph G { A -> B -> C; A -> C; })
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

![](http://g.gravizo.com/svg?digraph G { A -> B -> C; A -> C; })
