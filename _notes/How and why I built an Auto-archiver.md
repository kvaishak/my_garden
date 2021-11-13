---
title: How and why I built an Auto-archiver
---

Recently I had come across a wonderful application called ["WakaTime"](https://wakatime.com/). It is an automatic time tracking tool catering specifically for developers. Among the plethora of time tracking applications, what makes "WakaTime" unique is that it is entirely focused towards tracking and categorising the time spend on various coding languages and projects. WakaTime does this by having integrations with almost every IDEs and code editors. I was not able to find anything like WakaTime on the market and had soon grown fond of it.

## Why ?

Even though WakaTime is perfect for tracking ones coding metrics, I had to purchase their premium plan for saving my dashboard data for more than 2 weeks. Fortunately, I came across a Github project which updates a Github Gist with the last 7 days coding metrics automatically using Github actions.

This prompted me to build an archiver which will fetch my data from WakaTime automatically in a predefined interval and archive it.

## How ?

<img src="/assets/memehd.jpg">
