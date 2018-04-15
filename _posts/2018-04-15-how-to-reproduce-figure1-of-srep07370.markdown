---
layout: post
title:  "How to reproduce Figure 1A of srep07370"
author: Daniel Kim
categories: Publication
tags: publication figure
cover:  "/assets/images/DKim2014/Fig1.jpg"
---

[Daniel Kim *et al.* *Sci. Rep.* **4**:7370 (2014).](https://www.nature.com/articles/srep07370)

This is one of my representative papers. It was posted on [*Nature.com*](https://www.nature.com/), being selected as a [Nature Research Highlight](http://www.natureasia.com/en/research/highlight/9640) (also held the first rank of the most viewed research highlight on Nature.com from 14 December 2014 to 14 January 2015). [Full list of media press.](http://danielykim.me/papers/DKim2014/)

Here I introduce the way to plot Figure 1A of the paper in detail.

## 1. Save color usages as file.
Suppose we've already got rank ordered usages for each color.

Let's save rank ordered color usages as a tab separated file without header. 

For example, if we have the following table,

| Rank | Color Usage | Red | Green | Blue |
|---|--|--|--|--|
| 1 | 0.003395 | 228 | 236 | 239 |
| 2 | 0.003363 | 227 | 235 | 238 |
| 3 | 0.002813 | 229 | 237 | 240 |
| 4 | 0.002767 | 224 | 233 | 238 |
| 5 | 0.002750 | 202 | 229 | 240 |

where Color Usage is normalized and 0 ≤ Red, Green, Blue ≤ 255.

A tab separated file will be

```
1	0.003395	228	236	239
2	0.003363	227	235	238
3	0.002813	229	237	240
4	0.002767	224	233	238
5	0.002750	202	229	240
```

## 2. Install Gnuplot.
You may download [Gnuplot](http://www.gnuplot.info/) [here](https://sourceforge.net/projects/gnuplot/).

Please install it.


## 3. Draw
You can draw your own tsv file with the following Gnuplot script.

### Example
As an example, download `schloss.tsv` at [here](https://github.com/danielykim-dev/reproduce-my-figures/blob/master/DKim2014-srep07370/schloss.tsv).

Copy and paste the below code into a file. Its extension should be `plt`.

<script src="https://gist.github.com/danielykim/ede297311b4da18ed494475b63a89e9c.js"></script>

<style>
.gist .blob-code {
  padding: 1px 20px !important;
}
</style>

Now, let's double click the `plt` file. Then the figure will be shown. It may take over 10 seconds.

Replace `schloss.tsv` with your own file path, and check your figure.
