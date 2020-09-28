# Git Standard Operating Procedures.

## Overview
This is an overall strategy we will aim for. Please note that different projects may have needs and so may have different procedures and we may change or refine our process as we learn how to work with each other better.

Always check the documentation of the project you are working on, ask your teammates questions and verify with them your understanding. This is good practice for good communication especially when working on a remote and asynchronous environment

### Feature branches
We will be using the rebase and merge strategy for keeping our history clean. If you have not yet worked using this strategy, check out this [tutorial](https://www.atlassian.com/git/tutorials/merging-vs-rebasing) online.

We highly recommend using a tool such as GitKraken or SourceTree to help you visualize what is going on with the history and your current place in it.

### Merging into master
We will use regular merge commits or squash commits for merging feature branches into master so that we can keep track of master's history.

## Important Rules to live by:
- [ ] Keep your master up-to-date and your feature branch up to date with your master. Don't let your branch fall behind as this will give you more and more headaches whenever there are merge conflicts the longer you wait to update. Do this before starting work and as often as you can when you see that master has moved.
- [ ] Keep your branch/commit small. Keep to the purpose of your branch to the issue or feature you are implementing. The more concise, the better and the easier to code review.
- [ ] Squash commits that are related. Don't keep any test commits that don't tell a useful story of what is going on. Ideally, when you make your Pull Request, you will only have one commit. Try to squash before you rebase as you will quickly find out what a pain it is to resolve merge conflicts when there are so many commits you have to review.
- [ ] Review what you are adding to your commit. Ignore irrelevant formatting changes when it's not related to your work as this clutters up the diff.
- [ ] Make commit messages verbose. Include a title, description, the issue number(s), and explanation of what has changed and why.

## The Steps

### Creating your branch

1. Update master
   ```bash 
   git checkout master
   git pull origin master
   ```

2. Create your new feature branch. Use a similar pattern:
   ```
   <issue/feature/bugfix/hotfix/doc/refactor>/<issue number>/<title>
   ```

   ```bash
   git checkout -b issue/123/x-route
   ```

### While Developing

1. Make your changes, create commits
   ```bash
   git add .
   git commit -m 'commit message'
   ```

2. Update your branch with master
   ```bash
   git checkout master
   git pull
   git checkout <your branch>
   git rebase master
   ```

5. Fix any conflicts. You will notice, if you have a lot of commits in your branch, and there are conflicts, you may end up having to resolve many things over and over. This is why it's important to make sure to squash related commits.
6. Ensure your code is has relevant tests as much as possible.

### Preparing for a pull request
1. Do an [interactive rebase](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History). It is highly recommended for those less comfortable with command line Git to use [Sourcetree](https://www.atlassian.com/blog/sourcetree/interactive-rebase-sourcetree)
2. Start an interactive rebase. With source tree, you check out your branch, right click on master and choose to rebase interactively.
3. Make sure all your tests pass including lint.
4. Sqash your commits together
5. Make sure that you are only committing the files and changes you intended to make.
6. Prepare your overall commit message. If someone helped you with your code, give them credit by adding them as co-authors

   **Example commit message:**
   ```bash
   Updating the documents with new SOP

   Co-authored-by: name <name@example.com>

   Related Issue #145

   Why:
   Our documentation is outdated and no longer reflects what we actually do.

   Changes:
   - We no longer use develop branches so we are updating to only use master
   - Adding emphasis on using rebasing and keeping up with
   master.
   ```
   Make sure to not use long lines

7. Push your changes
   Rebasing or changing any history will reject a normal ``git push``, so you will have to do a force push
   ```bash
   git push -f origin <your branch>
   ```

### Go to GitHub and create your Pull Request
1. Make sure the PR description is accurate and verbose like your commit message. Add any relevant screenshots if you are making front end changes.
2. If you are not ready for your PR to be reviewed and just want to see how it runs in the CI or want feedback before you are done with your work, create it as a draft.
3. Make sure tests are passing in the CI
4. Request for your PR to be reviewed by an admin

### After you get your feedback
1. Address feedback and make necessary changes. You may need to do a back and forth more than once. Don't be in a hurry to get your changed merged in. Code Reviews are learning and experience gaining opportunities for both reviewer and reviewee.
2. Clean up your Git history again with squashes and ensure your commit is clean and concise and your commit message reflects the changes you made before your changes are merged.
3. Once tests are passing and you have admin approval, you or an admin may merge your pull request.
4. Confirm your changes. After your changes have been merged into master, if automatic deployment is available, check your deployed work in the environments you have access to to make sure it's working the way it should.
5. Cleanup. After your branch has been merged and/or is no longer needed, delete your branch from GitHub and your local machine.
