# Git Standard Operating Procedures.

## Overview
We will be using the rebase and merge strategy for keeping our history clean. As a safety net, only 'Rebase and merge' has been disabled for all our repositories. If you have not yet worked using this strategy, check out this [tutorial](https://www.atlassian.com/git/tutorials/merging-vs-rebasing) online.

We highly recommend using a tool such as SourceTree to help you visualize what is going on with the history and your current place in it.

## Important Notes:
* Keep your master and your branches up-to-date. Don't let your branch fall behind as this will give you more and more headaches whenever there are merge conflicts the longer you wait to update. Do this before starting work and whenever you see that master has moved.
* When making commits, group together by purpose so that it is easier to see what has changed. Ignore irrelevant formatting changes when it's not related to your work as this clutters up the diff.

## The Steps

### Update master
```
git checkout master
git pull origin master
```

### Naming Branches
For issues
```
<your gh username>/issues/<issue number>-<issue-title>

example:
ambergkim/issues/15-fixing-404-route
```

For features
```
<your gh username>/feature/<feature-title>

example:
ambergkim/feature/adding-user-route
```

For documentation
```
<your gh username>/docs/<doc-title>

example:
ambergkim/docs/github-workflow
```

### Create Your Branch
Create your new branch while you are on master so that you are autmatically branched from master. Example:
```
git checkout -b ambergkim/docs/github-workflow
```

### Rebasing an Existing Branch
After you have updated your master with the remote master, check out your existing branch then do:
```
git rebase master
```
Resolve all your conflicts then push up to your remote branch. You may have to do a
```
git push -f origin <your branch name>
```

### Writing Your Commit Messages
If you are in the middle of your work but want to save your work in the cloud for safety, begin your commit message with 'in progress,' so that we know your work is still ongoing.

### A-C-P
After you make a set of changes
```
git status
git add .
git commit -m '<your message here>'
git push
```

### Squash Your Related Commits
If you're not a command line guru, we highly recommend you use SourceTree's interactive rebase to do this so that you can have visual feedback of what you are doing.

Squashing your related commits will get rid of history that's not important. We don't care how you turned left then right then left and right in order to get to your final destination. We only want to know that you got to the end.

Don't squash all your commits into one if they are unrelated. If you added one feature and then added a change to the documentation and tests for this feature, it's ok to squash them together, but if the tests or documentation address something else, keep them separated.

After squashing you may have to do this to be able to push your changes
```
git push -f origin <your branch name>
```

### Ensure Tests Are Passing
Make sure your tests are passing before you create your pull request
```
npm run test
```

### Creating Your Pull Request
Create your pull request to master. Assign a merge master and any relevant folks to review your code. It is important to have a good description of what your pull request is all about. Include this information in your pull request when relevant:
- [ ] Descriptive but concise title
- [ ] The problem you are trying to solve
- [ ] Your approach to solving the problem
- [ ] What is the current state
- [ ] What is the state after you've made your changes

### Applying Feedback
Treat your new commits from addressing your feedback just like your previous commits. Related commits need to be squashed into one commit. For example, you added a new feature then created a pull request for it. Then you made a new commit to address requested changes to your feature. The new changes need to be squashed into your original commit. The commits may not be in the correct order for squashing, so doing an interactive rebase is very useful for this. Check out this tutorial in how to do this with [Sourcetree](https://www.atlassian.com/blog/sourcetree/interactive-rebase-sourcetree).

### Merging
Merging will be done by merge masters

### Cleanup
After your branch has been merged and/or is no longer needed, you may delete your branch from GitHub and your local machine.