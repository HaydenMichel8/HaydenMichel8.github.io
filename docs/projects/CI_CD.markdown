---
layout: default
title: CI_CD
permalink: /CI_CD/
---
[Return to Projects](/projects/)

### Refactor of naming check with cxxheaderparser

One of the jobs in the CI/CD pipeline was checking the naming of all elements in .cpp and .hpp files such as variables, namespaces, and everything else that gets named. All of these elements have specific rules for which case should be used, for example LOUD_SNAKE_CASE should be used for constant variables. There are a ton of very specific rules and exceptions. My task was to update the naming check to use the modern and lightweight cxxheaderparser python module. This greatly improved the speed and fixed memory leak errors that the previous clang implementation was causing. 
My commit adding this change is on the opensource version of NavToolKit it was for: [github commit link](https://github.com/is4s/NavToolkit/commit/1021667acd6f8ee47e8cc08500f0b06b30200bea#diff-9bdebf465a6473b168e391d993304d02a707f1347c83a23cfa800fb23757ade9)

Here is a link to the python file I wrote to run the naming rules check: [github file link](https://github.com/is4s/NavToolkit/blob/main/util/check_naming.py)

This was my first major project an my internship for IS4S and my first time making a merge request. I got a ton of comments and learned a lot about how to write good readable code from this process. It was pretty difficult to account for every exception so I started opening issues and pushing changes to the source code of [cxxheaderparser](https://github.com/robotpy/cxxheaderparser), which eventually got merged or fixed by the maintainer. This was my first time truly contributing to open-source code other people actually use and it felt pretty cool to know that my contributions made this tool just a little bit better.

### Implementing ruff

[ruff](https://docs.astral.sh/ruff/) is a new python tool for linting and formatting code. I read about it online and saw how much faster it could be so I decided to try and update the existing CI/CD pipelines for some of our projects to use it. This process was more difficult than I anticipated because almost everyone has an opinion on what the correct way to format code is, so it was difficult to get a consensus on what the right rules to use were before migrating from flake8 and black to ruff. This change sped up the CI/CD pipelines, combined 2 of them into 1, and allowed for new capabilities like sorting imports which we previously were not doing in the existing codebase. At my internship we used Gitlab which I had never seen before so it was interesting to learn about how to set up and change the CI/CD pipelines for it.
