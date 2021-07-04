---
layout: post
title: "End of Week Three"
date: 2021-06-27
categories: gsoc
---

<p align="center">
  <img src="/images/gsoc-logo.png" width=400 height=200>
</p>
<p align="center">
  <img src="/images/mlpack-logo.png">
</p>

This was an exciting week. I was finally going to remove `load.cpp` but well, when does it go according to plan.
As soon as I removed `load.cpp` I was bombarded with include errors(which was expected). Upon solving some we realised that the `load.hpp` might require some changes in the way it defines fucntions. At this point [Omar](https://github.com/shrit) suggested to use `SFINAE`.

You can see [here](https://github.com/mlpack/mlpack/wiki/DesignGuidelines#template-metaprogramming-and-sfinae) how mlpack utilizes `SFINAE`.

This was a new concept for me. Omar helped me out with a basic example to get me started on it. After some initial struggle and understanding thanks to [Ryan](https://github.com/rcurtin) who took out time and took a small 15 minute session on `SFINAE` and how it is used in mlpack.

I have my concepts a bit clear now, but this task made me realise that there is a lot in C++ which I still need to learn. To follow up on this I've decided to dedicate some time daily to study modern C++.

I found this [YT Channel](https://www.youtube.com/user/CppCon/videos) very helpful to get a deep dive on the concepts. They also have their github repo links which contains presentaions and other materials used in the conferences.

Next week we are planning to start removing the `boost::spirits` and connecting the `DatasetMapper` with the new parser's implementation. I will also update more on how I handled `SFINAE`.


