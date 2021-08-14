---
title: "Experience: Week Eight"
date: "2021-08-01"
template: "post"
draft: false
slug: "week-eight"
category: "GSoC"
tags:
  - "GSoC"
  - "Open Source"
  - "Mlpack"
  - "Weekly update"
description: "Exciting week. We removed Load.cpp.
              Added new string algorithms. There
              were awesome discussions on IRC. It's
              great to be a part of this community."
---

![mlpack-logo.png](/media/mlpack-logo.png)
![gsoc-logo.png](/media/gsoc-logo.png)

This was an exciting week. We were finally able to remove `Load.cpp`. There were some header
related issues that we had to handle but nothing tough apart from that just remove it from
`CMakelists.txt` and we are good to go.

Talking about the failing cases, it seems that our new fucntion signature where we replaced
`eT` with `MatType` was causing this issue. The main issue was that compiler was not able to
understand the difference between the signature of `Load` for dense matrix and sparse matrix.
For now we commented the code related to sparse matrix and decided that we will handle that
later.

We also worked on adding some string-related algorithms to mlpack. We created a new file
[`string_algorithms.hpp`](https://github.com/mlpack/mlpack/blob/3be9474388a42f74be0f0119346080a539a05e6b/src/mlpack/core/data/string_algorithms.hpp) and added the same to `CMakeList.txt`. For start the file contains
the string related fucntions which mlpack was utilizing from `boost`. List of functions

* trim
* trim_if

Replacing these two fucntionalities marks the end of `boost::spirit` in mlpack. We were able
to remove `boost` from the `csv parse` and we will remove other fucntion soon.

Discussion is still goinging on about how to perfectly parse the categorical data. Specially
data with embedded delim inside the string, ex `1, 2, "sting, with comma", 4`.

Implementing the categorical parsing part is fun, there are soo many things we can do but
currently we are sticking with implementing only the features that we had earlier and
currate a list for future improvements.

I know it feels a bit bad to see that there is scope for improvement but not exploring it
but [Omar](https://shrit.me/) made me realize that this is part of software development process. The project
is time constrained and first we need to finish and merge the parse and then we can think
about improvements, which really seems logical and systematic.

Also in open-source maybe community maybe someone can come-up with a better solution so
we should always give some time and discussion on what we are planning to accomplish.
Mlpack is great, `IRC` is soo active and it's alway some discussion that you can learn
from.

