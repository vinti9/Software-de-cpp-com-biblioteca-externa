# Markdown Rendering

A First Level Header
====================

A Second Level Header
---------------------

Now is the time for all good men to come to
the aid of their country. This is just a
regular paragraph.

The quick brown fox jumped over the lazy
dogs back.

### Header 3

> This is a blockquote.
>
> This is the second paragraph in the blockquote.
>
> ## This is an H2 in a blockquote

Code Cells
==========

```python
import numpy as np
import seaborn as sns

sns.distplot(np.random.rand(100).tolist())
```
```{python}
import numpy as np
import seaborn as sns

sns.distplot(np.random.rand(100).tolist())
```

Latex, gif/images
=================

### Render Latex

```{mathjax}
$$\begin{array}{r l}
\max & z = \sum_{j=1}^{n} c_j x_j & \\
\text{s.t.} & \sum_{j=1}^{n} \bar a_{ij} x_{j} + \max_{S_i \subseteq J_i, |S_i| = \Gamma_i} { \sum_{j \in S_i} \hat a_{ij} y_j } \leq b_i & \forall\, i=1,\dotsc,m \\
& x_j \leq y_j & \forall\, j=1,\dotsc,n\\
& x_j \geq 0,y_j \geq 0  & \forall\, j=1,\dotsc,n
\end{array}$$
```

```mathjax
$$\begin{array}{r l}
\max & z = \sum_{j=1}^{n} c_j x_j & \\
\text{s.t.} & \sum_{j=1}^{n} \bar a_{ij} x_{j} + \max_{S_i \subseteq J_i, |S_i| = \Gamma_i} { \sum_{j \in S_i} \hat a_{ij} y_j } \leq b_i & \forall\, i=1,\dotsc,m \\
& x_j \leq y_j & \forall\, j=1,\dotsc,n\\
& x_j \geq 0,y_j \geq 0  & \forall\, j=1,\dotsc,n
\end{array}$$
```

### Render images and gifs

![](http://i.giphy.com/j5QcmXoFWl4Q0.gif)

Lists
=====

*   Candy.
*   Gum.
*   Booze.

+   Candy.
+   Gum.
+   Booze.

-   Candy.
-   Gum.
-   Booze.

1.  Red
2.  Green
3.  Blue

Links
=====

This is an [example link](http://example.com/).

This is an [example link](http://example.com/ "With a Title").

I get 10 times more traffic from [Google][1] than from
[Yahoo][2] or [MSN][3].

[1]: http://google.com/        "Google"
[2]: http://search.yahoo.com/  "Yahoo Search"
[3]: http://search.msn.com/    "MSN Search"

I start my morning with a cup of coffee and
[The New York Times][NY Times].

[ny times]: http://www.nytimes.com/

Images
======

![alt text](/path/to/img.jpg "Title")

![alt text][id]

[id]: /path/to/img.jpg "Title"

Codes
=====

I strongly recommend against using any `<blink>` tags.

I wish SmartyPants used named entities like `&mdash;`
instead of decimal-encoded entites like `&#8212;`.

If you want your page to validate under XHTML 1.0 Strict,
you've got to put paragraph tags in your blockquotes:

    <blockquote>
        <p>For example.</p>
    </blockquote>

Highlight
=========

==Highlight==

<mark>Marked text</mark>

<span style="background-color: #FFFF00">Marked text</span>

<code> _Hello_ **world** </code>

```
    first level

    ```
    second
    ```

```

<span class="keyword">This should be styled like a keyword</span>

<span class="entity name function"> This should be styled similar to a function within the color scheme</span>

