---
title: Hi Hugo
author: Mathew Gluck
date: '2021-04-30'
slug: []
categories: []
tags: []
meta_img: images/image.png
description: Description for the page
---
# A test post

I want to type some inline math that is outside of _fenced in_ code and I hope it will render. Let's see: `\(a^2 + b^2 = c^2\)`. Nice. I would also like to type some displayed equations: 
`\begin{equation*}
    a^2 + b^2 = c^2
\end{equation*}`

Now how about some fenced in code. I'll try a theorm environment: 
<div class="theorem"><span class="theorem" id="thm:unnamed-chunk-1"><strong><span id="thm:unnamed-chunk-1"></span>Theorem 1  </strong></span>If <span class="math inline">\(a\)</span> and <span class="math inline">\(b\)</span> are the lengths of the legs of a right triangle, and if <span class="math inline">\(c\)</span> is the lenght of the hypotenuse, then <span class="math display">\[\begin{equation*}
    a^2 + b^2 = c^2. 
\end{equation*}\]</span></div>

I also believe I can insert Python code: 

```python
import numpy as np
a = np.arange(5)
a
```

```
## array([0, 1, 2, 3, 4])
```

This is just a check to be sure that my changes are being updated
