---
title: Configuring the bot on your reposiory
summary: An recaptime-config.yml file is need to make some features work such as Stale and others.
---

In order to make our GitHub bot work in your repository, you need to

## The Template

The template you see below is the configuration available for this bot. While we combining different Probot-powered apps into our own, we disable some automated actions that contains default configuration. What you see below are adopted from different apps such as [Stale](https://npmjs.com/probot-stale) and others.

```yml
# The following code must be use in your .github/recaptime-config.yml file
# to avoid the messy weekends (aka "the bot isn't working") on your repo
# where this app installed.

# Part 1: probot-stale

# Number of days of inactivity before an Issue or Pull Request becomes stale
daysUntilStale: 30

# Number of days of inactivity before an Issue or Pull Request with the stale label is closed.
# Set to false to disable. If disabled, issues still need to be closed manually, but will remain marked as stale.
daysUntilClose: 7

# Only issues or pull requests with all of these labels are check if stale. Defaults to `[]` (disabled)
onlyLabels: []

# Issues or Pull Requests with these labels will never be considered stale. Set to `[]` to disable
exemptLabels:
  - pinned
  - security
  - help needed

# Set to true to ignore issues in a project (defaults to false)
exemptProjects: false

# Set to true to ignore issues in a milestone (defaults to false)
exemptMilestones: false

# Set to true to ignore issues with an assignee (defaults to false)
exemptAssignees: false

# Label to use when marking as stale
staleLabel: stale

# Comment to post when marking as stale. Set to `false` to disable
markComment: >
  Hi, contributor!

  This issue has been automatically marked as stale because it has not had
  recent activity. It will be closed if no further activity occurs after X days/weeks/months. Thank you
  for your contributions.

  Friendly regards,
  @staff-username-here
# Comment to post when removing the stale label.
unmarkComment: >
   Hi, friend!

   Because our bot detected an new activity in this issue, we frankly cancelled our scheduled issue/PR closure
   for this one. To keep discussions alive, make sure you follow up to other contributors' replies and also
   from our staff. Thanks for your contributions and accept our apologies.

   Friendly regards,
   @staff-username-here
# Comment to post when closing a stale Issue or Pull Request.
# closeComment: >
#   Your comment here.

# Limit the number of actions per hour, from 1-30. Default is 30
limitPerRun: 30

# Limit to only `issues` or `pulls`
# only: issues

# Optionally, specify configuration settings that are specific to just 'issues' or 'pulls':
# pulls:
#   daysUntilStale: 30
#   markComment: >
#     This pull request has been automatically marked as stale because it has not had
#     recent activity. It will be closed if no further activity occurs. Thank you
#     for your contributions.

# issues:
#   exemptLabels:
#     - confirmed

```

Continue reading below for help in specific parts and parameters.

### Stale Issues/PR Management Configuration

Let's start configuring our bot first on managing inactive issues and pull requests. In **probot-stale**, there are three seperate configurations: one for repository-wide, one for issues and one for pull requests

#### Repository-wide Configuration

