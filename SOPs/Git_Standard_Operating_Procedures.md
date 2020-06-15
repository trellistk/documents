# Git Standard Operating Procedures.

## Overview
We will be using the rebase and merge strategy for keeping our history clean. As a safety net, only 'Rebase and merge' has been enabled for all our repositories. If you have not yet worked using this strategy, check out this [tutorial](https://www.atlassian.com/git/tutorials/merging-vs-rebasing) online.

We highly recommend using a tool such as SourceTree to help you visualize what is going on with the history and your current place in it.

## Important Notes:
* Keep your master up-to-date. Don't let your branch fall behind as this will give you more and more headaches whenever there are merge conflicts the longer you wait to update. Do this before starting work and whenever you see that master has moved.
* When making commits, group together by purpose so that it is easier to see what has changed.
* Squash commits that are related. Don't keep any test commits that don't tell a useful story of what is going on. Ideally, when you make your Pull Request, you will only have one commit.
* Keep commits small
* Make commit messages verbose. Include a title, description, the issue number(s), and explanation of what has changed and why.
* Ignore irrelevant formatting changes when it's not related to your work as this clutters up the diff.

## The Steps

1. Update master
```
git checkout master
git pull origin master
```
2. Create your new feature branch
Use a similar pattern:
```
<issue/feature/bugfix/hotfix/doc/refactor>/<issue number>/<title>
```

```
git checkout -b issue/123/x-route
```

3. Make your changes, create commits
```
git add .
git commit -m 'commit message'
```

4. Update your branch with master
```
git checkout master
git pull
git checkout <your branch>
git rebase master
```

5. Fix any conflicts. You will notice, if you have a lot of commits in your branch, and there are conflicts, you may end up having to resolve many things over and over. This is why it's important to make sure to squash related commits.

6. Preparing for a pull request
Do an [interactive rebase](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History). It is highly recommended for those less comfortable with command line Git to use [Sourcetree](https://www.atlassian.com/blog/sourcetree/interactive-rebase-sourcetree)
- Start an interactive rebase. With source tree, you check out your branch, right click on master and choose to rebase interactively.
- Sqash your commits together
- Prepare your overall commit message
Example commit message:
```
Updating the documents with new SOP
Issue#145

Changes:
- We no longer use develop branches so we are updating
to only use master
- Adding emphasis on using rebasing and keeping up with
master.
```
Make sure to not use long lines

7. Push your changes
Rebasing or changing any history will reject a normal ``git push``, so you will have to do a force push
```
git push -f origin <your branch>
```

8. Go to GitHub and create your Pull Request
- Make sure the PR description is accurate and verbose
- If you are not ready for your PR to be reviewed, create it as a draft
- Make sure tests are passing
- Request for your PR to be reviewed

9. After getting your review
- Address feedback and make necessary changes
- Clean up your Git history again with squashes and ensure your commit is clean and small.

10. Once tests are passing and you have admin approval, you may merge your pull request.

11. Testing
After your changes have been merged into master, if automatic deployment is available to a testing envrionment, check your deployed work to make sure it's working

12. Cleanup
After your branch has been merged and/or is no longer needed, you may delete your branch from GitHub and your local machine.

13. After your work has been tested and we are ready, your work will be deployed to production once a release has been created.