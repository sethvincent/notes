# GitHub Flow

## Overview
- Anything in the master branch is deployable
- To work on something new, create a descriptively named branch off of master (ie: new-oauth2-scopes)
- Commit to that branch locally and regularly push your work to the same named branch on the server
- When you need feedback or help, or you think the branch is ready for merging, open a pull request
- After someone else has reviewed and signed off on the feature, you can merge it into master
- Once it is merged and pushed to ‘master’, you can and should deploy immediately

*More detailed description: http://scottchacon.com/2011/08/31/github-flow.html*

## When is this useful?
This is a good workflow to use on most situations. It's particularly well-suited to projects like npm/pypi packages or for publishing docker containers to a docker registry. It can also be used for websites and applications when paired with continous deployment where publishing is tied to release tags. With this workflow the latest push to master can trigger tests, linting, and deployment to staging, while any release tag created will deploy to production.

## What are the drawbacks?
If there are multiple deployment environments beyond staging and production, the workflow will need to be extended to meet those needs.
