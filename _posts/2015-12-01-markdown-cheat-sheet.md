---
layout: post
title: Markdown Cheat Sheet
subtitle: "Examples of how to do it."
date:   2015-12-01 21:00:00
categories: [setup]
---

This is a post for me to reference with markdown on it, so I know what the syntax is. It is based on this [markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) tweaked for Kramdown.

### Headers

# H1

## H2

### H3

#### H4

### Text effects

Emphasis, aka italics, with *asterisks* or _underscores_.

Strong emphasis, aka bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

<s>use HTML element for strikethrough</s>

Subscript <sub>text</sub> must be done using using HTML

Superscript <sup>text</sup> also with HTML

### Lits

1. First ordered list item
2. Another item
  * Unordered sub-list.
1. Actual numbers don't matter, just that it's a number
  1. Ordered sub-list
4. And another item.

   You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

   To have a line break without a paragraph, you will need to use two trailing spaces.  
   Note that this line is separate, but within the same paragraph.  

* Unordered list can use asterisks (or hyphen or plus)

### Links

[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

Use angle brackets to get a link <http://www.example.com>

### Images

Inline-style:
![alt text](/assets/images/test-image.png "Logo Title Text 1")

Reference-style:
![alt text][logo]

[logo]: /assets/images/test-image.png "Logo Title Text 2"

### Tables

Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3


### Code

Some code here...

{% highlight js %}
// little snippet
angular.module('myApp')
  .controller('MainCtrl', function() {
      this.awesomeThings = [
        'angularjs',
        'javascript',
        'lodash'
      ];
  });
{% endhighlight %}

### Gists

Embed a gist like this...

{% gist 5555251 gist.md %}


### Blockquotes

> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote.

### Inline HTML

You can also use raw HTML in your Markdown, and it'll mostly work pretty well.

<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>

### Horizontal Rule

Three or more hypens (or asterisk or underscore)

---

### Equations

Using [MathJax](http://www.mathjax.org/).

Inline: $$ \varphi = \frac{1+\sqrt{5}}{2} = 1.61803\,39887\ldots. $$

Block:

$$

\int_0^{2\pi}\sin{x}\ dx=0
$$
