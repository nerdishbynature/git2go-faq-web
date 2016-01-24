---
layout: post
title: How to use URL schemes
---

Since version 1.5 (released on 25 Feb 2016) we added support for url schemes that lets you integrate with Workflow or 1Writer (or just you own custom scripts). This article should be an overview of all routes available and how to use them.

Unfortunately numbers are forbidden in URL protocols so our base scheme is `gittogo://`. We structured the URL schemes `REST` like.

### `repositories/:type/:owner/:name`

All access points share one base route for the moment: `repositories/:type/:owner/:name` owner and name should be self explanatory so if your repository is `https://github.com/nerdishbynature/OctoKit.swift` then `owner` is `nerdishbynature` and `name` is `OctoKit.swift`.
Types is where it gets interesting, available types are:

* `github` for GitHub.com repositories
* `bitbucket` for Bitbucket.org repositories
* `gitlab` for GitLab.com repositories
* `gh_enterprise` for GitHub Enterprise repositories
* `gitlab_enterprise` for self-hosted GitLab instances

More types will follow but these hosters are all we currently integrate with.

Just calling this route will simply switch the current repository to the repository from the route. **If the repository is not yet cloned the call will simply fail**

### `repositories/:type/:owner/:name/commits`

Calling this route will select the Commits or History tab in the TabBar.

### `repositories/:type/:owner/:name/branches`

Calling this route will select Branches tab in the TabBar

### `repositories/:type/:owner/:name/files`

Calling this route will select the Files tab in the TabBar

### `repositories/:type/:owner/:name/file/new`

Calling this route will select the files tab and create a new file with the given path and the content.

Mandatory parameters:

* `path` – The path including the file name, e.g. `_posts/2016-02-24-14-How-To-Use-URL-Schemes.md`
* `content` – The URL encoded content of the file

This gives you the opportunity to create files in other apps and then use the automation actions to save the file. For 1Writer the action looks like the following: `gittogo://repositories/github/nerdishbynature/git2go-faq-web/files/new?content=[text]&path=_posts/[text]`. You can install this action from the [1Writer Website](http://1writerapp.com/action/cc29f)