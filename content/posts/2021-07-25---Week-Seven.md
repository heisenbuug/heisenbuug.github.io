---
title: "Experience: Week Seven"
date: "2021-07-25"
template: "post"
draft: false
slug: "week-seven"
category: "GSoC"
tags:
  - "GSoC"
  - "Open Source"
  - "Mlpack"
  - "Weekly update"
description: "Nearly done with removing boost::spirit. Although I need to
              focus more on failing test cases and make necessary changes
              to the code. Boost was doing a lot of work behind the scenes,
              it kinda a lot of work to see and replace eveything but it's
              fun to explore soo much code."
---

![mlpack-logo.png](/media/mlpack-logo.png)
![gsoc-logo.png](/media/gsoc-logo.png)

This week I continued my working on removing boost::spirit and nearly completed it. There are some
tests that are failing which takes priority this week.

This week I was feeling pretty good about the code, I think it might be due to the fact that now
I've spent soo much time with the codebase I can understand it better.

So basically I am nearly done replacing the boost. Actually we removed the parser part but still
need to check on what `boost::trim` was exactly doing and remove the `Load.cpp` file and make sure
it is not breaking the code.

[Conrad](https://github.com/conradsnicta) suggested another feature to speed up the parser,
this was his exact comment
```
In Armadillo 10.6 I've implemented a multi-threaded CSV reader with the help
of OpenMP directives.

The new code is in diskio::load_csv_ascii(), currently on lines 1618-1761
https://gitlab.com/conradsnicta/armadillo-code/-/blob/10.6.x/include/armadillo_bits/diskio_meat.hpp#L1618-1761

In essence, instead of converting each token directly after reading into a
numerical value, all the tokens in each line are first read into an array.
The stored tokens are then converted into numerical values, within a
parallelised loop.
```

We decided to work on this once we are able to integrate the current improved parser. This can be
a great speed up to the parser and I am really looking forward to working on it. Thank you Conrad
for reviewing the code and keeping an eye on the project.

Also while testing we kinda discovered a small bug. I opened an issue for the same. You can have a
look, [Mlpack not handling Quoted quotes](https://github.com/mlpack/mlpack/issues/3024)
when parsing non-numeric data.

I will work on it once I will complete my basic goal of replacing `boost`.

I will talk about some other failing cases next week as I am yet to work on them and hopefully
I will remove `Load.cpp` file in the coming week.
