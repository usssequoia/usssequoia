# How To Guide

## Website development: Tips and Tricks
### Git

This git repository is configured to run a website build workflow any time commits are pushed to the "web" branch on github. A second "main" branch also exists, and can be used for development improvements etc.


**How-tos**

* What if I made a bunch of commits all with the wrong name / email?
  * *Based on https://stackoverflow.com/a/1320317*
  * First, you should set your name and email to what you expect them to be in your git configuration. For example:
  
  ```shell
  $ git config --local user.name "Firstname Lastname"
  $ git config --local user.email "email@address.example"
  ```

  * The above settings should probably match whatever you're using for github so that your commits look like they belong to your account.
  * Next, with the name configured we can rewrite history for each commit starting from a single revision with the name and email we set up above.
  * Let's see what the starting point is:
  ```shell
  $ git log
  # Should return a list of each log statement with the newest at the top
  # by default. 
  commit da7175ae2d877eda533e7e4d6ab46f5f3839d48a (HEAD -> main)
  Author: Firstname Lastname <email@address.example>
  Date:   Sun Jan 19 21:06:12 2025 -0800

      Some more initial setup a...
  ```
  * Each entry of the log will have a commit-id (SHA Hash) used to uniquely identify the changes and metadata (including the message, author, etc) in a revision. In the above example, `da7175ae2d877eda533e7e4d6ab46f5f3839d48a`, which we'll use in the next step.
  * This will start at the specified revision, and apply the new default name and email to each revision newer than the one specified.
  ```shell
  $ git rebase -r da7175ae2d877eda533e7e4d6ab46f5f3839d48a --exec "git commit --amend --no-edit --reset-author"
  ```


