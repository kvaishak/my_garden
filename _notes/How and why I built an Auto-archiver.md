---
title: How and why I built an Auto-archiver
---

Recently I had come across a wonderful application called ["WakaTime"](https://wakatime.com/). It is an automatic time tracking tool catering specifically for developers. Among the plethora of time tracking applications, what makes "WakaTime" unique is that it is entirely focused towards tracking and categorising the time spend on various coding languages and projects. WakaTime does this by having integrations with almost every IDEs and code editors. I was not able to find anything like WakaTime on the market and had soon grown fond of it.

## Why ?



Even though WakaTime is perfect for tracking ones coding metrics, I had to purchase their premium plan for saving my dashboard data for more than 2 weeks. Fortunately, I came across a Github project which updates a Github Gist with the last 7 days coding metrics automatically using Github actions.

This prompted me to build an archiver which will fetch my data from WakaTime automatically in a predefined interval and archive it.

## How ?

<img src="/assets/archiver.svg" />

I have uploaded my code in [Github](https://github.com/kvaishak/archiver) and it works without the need of any other service just by utilising the Github Actions as follows.

1. Once the node server starts it fetches my data from WakaTime in two ways -
   - A simple API call that Wakatime provides in the format of 'https://wakatime.com/api/v1/users/{username}/stats/last_7_days' by replacing 'username' you can get your last 7 days. Documentations [here](https://wakatime.com/developers#stats).
   - You can get an embedded link to access your data from the WakaTime website.
2. These two API calls will fetch the latest data in JSON format whenever they are called.
3. Once the data is received, we can convert the data to a CSV format.
4. After authenticating with Google Drive API, we can upload the CSV data to Google Drive in google sheet format.
5. This archival process can be automated by using Github Actions which runs the code based on a schedule that we can specify. In this case, I schedule it to run every week.

In this manner, Weekly data of my coding metrics will be automatically uploaded to my Google drive, every week. Which I can aggregate and used for long term analytics and visualizations.

## Enhancements

Once I was done with WakaTime Automation, I added a similar archiving process for RescueTime, which is another Automatic Time tracking software, which tracks everything when compared to WakaTime. Since I don't have to archive Rescuetime data every week, I make it run on the first week of every new month and archives the entire previous months data.

Since the code is written in a modular fashion, I can add/remove any compactable Third-party service for fetching and saving my data to google drive.
