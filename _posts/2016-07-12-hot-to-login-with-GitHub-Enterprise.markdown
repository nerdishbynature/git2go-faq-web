---
layout: post
title:  "How to login with GitHub Enterprise"
date:   2016-07-12 10:43:00
---

## Steps

1. After opening the application __go to Settings__ (gear icon in the upper left)
2. __Select Remote Logins__, here you will find all your existing logins and you are able to login to GitHub, Bitbucket, GitLab, GitHub Enterprise and self-hosted GitLab installations
3. Tap on __GitHub Enterprise__
4. __Type in the URL__ you would normally use to access the installation in your browser, e.g. "https://git.nerdishbynature.com"
5. Tap __Get Access Token__
6. A web page will open and greet you with a pre filled form to create a new access token. Simply __press the green button__
	1. In order for Git2Go to work we need two scopes:
		1. repo – to list all of the users repositories and clone them to the device
		2. user – to get the users information (name, email) to pre fill the Git information used to make commits
7. __Copy the token__ from the web page (__important!__ For security reasons you will not be able to retrieve the token again from the website)
8. __Tap__ the __Done__ button
9. __Git2Go will automatically detect the token__ in the clipboard and fill it into the form
10. __Tap Connect__, Git2Go will now retrieve the users information and show it in the overview. All information will be stored on your device only - nothing is sent to remote servers.