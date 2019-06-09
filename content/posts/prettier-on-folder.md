---
title: "Run Prettier on a folder"
date: 2019-06-09T09:39:17-04:00
draft: false
---

While it's kinda weird question, sometimes you come with the need to run prettier (JS formatter) in a complete folder
but the documentation is not that clear on how to achieve it

Saw some people talking about using `xargs`, `find` and some other trickery to pass one file to the prettier binary
but that seemed quite odd. In the end found out it's as simple as doing:

```bash
cd your-project
npx prettier --config ./prettier.config.js --write src/**/**.js
```


What this does is to provide prettier with it's config so it doesn't have to search it for every file 
and run against all the files inside `src` including sub-folders but limiting the scope to js files otherwise
it would run even against CSS, LESS or any other type of file it finds.  