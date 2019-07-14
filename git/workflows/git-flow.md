# Git Flow

## Overview
- Two main branches: `master` and `develop`
  - `master` is production-ready code
  - `develop` is code that is ready for the next release
- A merge from `develop` to `master` is a new release
- Supporting branches:
  - Feature branches
    - must branch from and merge back into `develop`
    - can be named anything except `master`, `develop`, `release-*`, or `hotfix-*`
  - Release branches
    - may branch off from `develop`
    - must merge back into both `develop` and `master`
    - must be named with the `release-` prefix
  - Hotfix branches
    - may branch off from `master`
    - must merge back into both `develop` and `master`
    - must be named with the `hotfix-` prefix

*More detailed description: http://nvie.com/posts/a-successful-git-branching-model/*

## When is this useful?
Git Flow can be useful for complicated application and website workflows where publishing based on release tags on a single master branch isn't plausible for whatever reason. It might be a limitation of the CI or git hosting. This workflow allows any merge into the master branch to be deployed.

## What are the drawbacks?
It's more complicated than it needs to be. This workflow was first published in 2010, and I believe the multi-branch approach of using `develop` and `master` was a necessary complication based on the limited continuous integration services of the time. With services like GitHub Actions and Circle CI we can accomplish the important parts of the above workflow without the complexity of two long-running branches or the annoyance of dealing with hotfix branches.
