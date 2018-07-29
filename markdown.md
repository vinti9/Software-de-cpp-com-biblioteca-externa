# Tutorial de markdown

Alternatively, for H1 and H2, an underline-ish style:

Alt-H1
======

Alt-H2
------

## Citações

> Esta é uma citação

`Bloco`

**Negrito**

_Cursivo_

***Negrito e cursivo***

Link: [Google](www.google.com)

Imagem

![Computação](https://cdn.pixabay.com/photo/2016/04/04/14/12/monitor-1307227_1280.jpg)

![How to be productive](https://wordsofleisure.files.wordpress.com/2013/12/uberproductive.png)

![Icones de programção](https://st.depositphotos.com/1019970/4811/i/950/depositphotos_48119045-stock-photo-programming-language-icons.jpg)

![Data science](https://wrivdrdfe14093ot4amc3bc7-wpengine.netdna-ssl.com/wp-content/uploads/2017/08/CS-Data-Science.jpg)

Este é um `código`

    Bloco com <tab>

~~~
Bloco de testo
~~~

*Sem símbolos*

Anulando markdown: \*Com símbolos*

{com chaves}

# Lists

Unordered

* Item 1
* Item 2
 * Item 2a
 * Item 2b

Ordered

1. Item 1
2. Item 2
3. Item 3
 * Item 3a
 * Item 3b

# Emphasis

*This text will be italic*

_This will also be italic_

**This text will be bold**

__This will also be bold__

*You **can** combine them*

# Blockquotes

As Grace Hopper said:
> I’ve always been more interested
> in the future than in the past.

# Backslash escapes

\*literal asterisks\*

Markdown provides backslash escapes for the following characters:

\\ backslash

\` backtick

\* asterisk

\_ underscore

\{} curly braces

\[] square brackets

\() parentheses

\# hash mark

\+ plus sign

\- minus sign (hyphen)

\. dot

\! exclamation mark

# Fenced code blocks

```javascript
function test() {
 console.log("look ma’, no spaces");
}
```

```ruby
def index
  puts "hello world"
end
```

```csharp
private void index(){
  MessageBox.Show("hello world");
}
```

* bash ('*.sh', '*.ksh', '*.bash', '*.ebuild', '*.eclass')
* c ('*.c', '*.h')
* cmake ('*.cmake', 'CMakeLists.txt')
* cpp ('*.cpp', '*.hpp', '*.c++', '*.h++', '*.cc', '*.hh', '*.cxx', '*.hxx', '*.pde')
* gnuplot ('*.plot', '*.plt')
* make ('*.mak', 'Makefile', 'makefile', 'Makefile.*', 'GNUmakefile')
* python ('*.py', '*.pyw', '*.sc', 'SConstruct', 'SConscript', '*.tac')
* tex ('*.tex', '*.aux', '*.toc')

[Reference][f1d91e92]

  [f1d91e92]: https://support.codebasehq.com/articles/tips-tricks/syntax-highlighting-in-markdown "Link"

# username @mentions

Typing an @ symbol, followed by
a username, will notify that person
to come and view the comment.
This is called an “@mention”,
because you’re mentioning the
individual. You can also @mention
teams within an organization.

# Issue reference

Any number that refers to an Issue or
Pull Request will be automatically
converted into a link.

#1
github-flavored-markdown#1
defunkt/github-flavored-markdown#1

# Task Lists

- [x] this is a complete item
- [ ] this is an incomplete item
- [x] @mentions, #refs, [links](),
**formatting**, and <del>tags</del>
supported
- [x] list syntax required (any
unordered or ordered list
supported)

# Tables

You can create tables by assembling
a list of words and dividing them
with hyphens - (for the first row),
and then separating each column
with a pipe | :

First Header | Second Header
------------ | -------------
Content cell 1 | Content cell 2
Content column 1 | Content column 2

# Emoji

To see a list of every image we
support, check out
www.emoji-cheat-sheet.com

GitHub supports emoji!

:+1: :sparkles: :camel: :tada: :rocket: :metal: :octocat:

# Code and Syntax highlighting

Inline `code` has `back-ticks around` it.

```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

```python
s = "Python syntax highlighting"
print s
```

```
No language indicated, so no syntax highlighting.
But let's throw in a <b>tag</b>.
```

# Blockquotes

> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote.

# Horizontal Rule

Three or more...

---

Hyphens

***

Asterisks

___

Underscores

# Line Breaks

Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.

# Emphasis: bold and italic

This is **bold** and this is _italic_.

# Identifiers

[Text to display][identifier] will display a link.

[Another text][another-identifier] will do the same. Hover the mouse over it to see the title.

[This link] will do the same as well. It works as the identifier itself.

[This link][] (same as above), has a second pair of empty brakets to indicate that the following parenthesis does not contain a link.

<https://example.com> works too. Must be used for explicit links.

<!-- Identifiers, in alphabetical order -->

[another-identifier]: https://example.com "This example has a title"
[identifier]: http://example1.com
[this link]: http://example2.com

Link: https://about.gitlab.com/handbook/product/technical-writing/markdown-guide/

:kissing: :laughing: :neutral_face:

https://ourcodeworld.com/articles/read/162/tips-and-tricks-that-you-probably-don-t-know-with-the-github-markdown-in-readme-md-files

https://blog.ghost.org/markdown/

http://blog.virtuacreative.com.br/markdown-tips-and-tricks.html

http://www.emberdaily.com/2016/07/28/43-markdown/

https://www.renfei.org/snippets-lab/manual/mac/markdown.html

https://commondenominator.email/writing-with-markdown-for-better-content-html-why-how-to-whiteboard-friday/

# Text Effects

_Italic_

**Bo­ld**

~~Strikethrough~~


https://about.gitlab.com/2016/07/19/markdown-kramdown-tips-and-tricks/

https://steemit.com/tutorial/@sndbox/markdown-tutorial-steemit-blogging-tips

https://about.gitlab.com/2016/07/19/markdown-kramdown-tips-and-tricks/

http://habitica.wikia.com/wiki/Markdown_Cheat_Sheet

https://packagecontrol.io/packages/PlainNotes

https://community.stackedit.io/t/customize-preview-with-icon-fonts-and-custom-css/141

https://github.com/koncina/unilur

https://github.com/aziz/PlainNotes/blob/master/README.md

https://atom.io/themes/duotone-dark-sea-syntax

https://www.google.com.br/search?q=markdown+editing+color+scheme&source=lnms&tbm=isch&sa=X&ved=0ahUKEwj00_f_rcXcAhVIG5AKHXL0BzIQ_AUICigB&biw=1536&bih=744&dpr=1.25#imgdii=j_89lQienyAk1M:&imgrc=BLKVdVYjsi10yM:


http://simurai.com/projects/2016/01/01/duotone-themes

https://sdtuts.com/markdown-editors/

https://github.com/SublimeText-Markdown/MarkdownEditing
