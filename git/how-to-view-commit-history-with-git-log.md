# [How to View Commit History With Git Log – CloudSavvy IT](https://www.cloudsavvyit.com/13904/how-to-view-commit-history-with-git-log/)

![](https://www.cloudsavvyit.com/pagespeed_static/1.JiBnMqyl6S.gif) Aug 23, 2021, 7:00 am EST | 2 min read 

![Git logo](https://www.cloudsavvyit.com/p/uploads/2019/10/e713ed70-1.png?width=1198&trim=1,1&bg-color=000&pad=1,1)

Git tracks commits over time, allowing you to follow the progression and history of your code. While you can always use Github online to view the public repository, navigating your local repo requires the use of CLI tools to view the Git commit history, like `git log`.

## The Non-CLI Solution: Just Use a Git Client

While you should definitely learn to use Git from the command line, as it helps to understand everything you’re doing, this is one of the few times where it really does just make more sense to have a proper interface for viewing Git history, especially when you take into account multiple branches, remotes, tags, and contributors. The experience of using online services like GitHub is clearly beneficial, so why not have it on the desktop?

![](https://www.cloudsavvyit.com/p/uploads/2021/08/df2310d5.png?trim=1,1&bg-color=000&pad=1,1)

There [are a lot of Git GUI clients out there](https://git-scm.com/downloads/guis), but the most notable ones are [Github Desktop](https://desktop.github.com/), [GitKraken](https://www.gitkraken.com/git-client), [Fork](https://git-fork.com/home), and [SourceTree](https://www.sourcetreeapp.com/).

However, it’s still useful to learn the commands. You might not want to use a GUI, or you may be in a remote environment over SSH, or you may just want a quick peek while you’re already at your terminal. Luckily, using `git log` is fairly easy.

## Using git log

By default, `git log` shows a lot of info about each commit—the ref ID, the author, the date, the commit message, and if it’s the HEAD of any branches.

git log

![](https://www.cloudsavvyit.com/p/uploads/2021/08/0f313b35.png?trim=1,1&bg-color=000&pad=1,1)

If you’d like to know what files are affected, you’ll need to run it with `--stat`, which will display a list of files with additions and deletions.

git log --stat

![](https://www.cloudsavvyit.com/p/uploads/2021/08/c47b0000.png?trim=1,1&bg-color=000&pad=1,1)

If you’d like to know what actually changed in these commits, you’ll need to run it with `-p`, which can be used with or without `--stat`:

git log --stat -p

![](https://www.cloudsavvyit.com/p/uploads/2021/08/9bff64fc.png?trim=1,1&bg-color=000&pad=1,1)

This can be a lot to filter through, so you can sort by date:

git log --after="2014-7-1" --before="2014-7-4"

Or view by affected file:

git log -- example.json

Or with a search string:

git log -S"Hello, World!"

Or view important merge commits:

git log --merges

And, if you just want to view the changes of a single commit from the log, you can copy the hash and run `git show`:

git show e9d802bdc3a61943b2c9c736194a202b4e000180

## Viewing Branch History

Just having a list of commits can be messy to sort out branches. Luckily `git log` provides the `--graph` option which can be used alongside some

git log --graph --oneline --decorate

![](https://www.cloudsavvyit.com/pagespeed_static/1.JiBnMqyl6S.gif)

You can also [use custom formatting](https://mirrors.edge.kernel.org/pub/software/scm/git/docs/git-log.html#_pretty_formats) if you don’t like the look of this:

\--pretty=format:"%cn committed %h on %cd"

This particular set of parameters is quite useful, but there isn’t a shorthand for it, so if you use this a lot, we recommend setting an alias in `~/.bashrc`, or whatever equivalent config you use for your shell:

alias gitgraph='git log --graph --oneline --decorate'

**RELATED:** [**_How to Create Aliases and Shell Functions on Linux_**](https://www.howtogeek.com/439736/how-to-create-aliases-and-shell-functions-on-linux/)