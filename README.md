Project Documentation:
----------------------------------------------
**Initial Commit: <br />**
Number guessing game created in main branch. 5 additional branches created which are direct descendents of main: dev, feature1, feature2, feature3, hotfix. Additionally, created documentation branch.

Branches and their changes:
----------------------------------------------
**dev: <br />**
Commits: Add encouraging message for players. <br />
Branches from main with a single commit.

**feature1: <br />**
Commits: Add ability to quit game with negative number input. Add play-again loop functionality. Improve user feedback messages for guesses. Add version comment documenting quit feature. <br />
Branches from main with 4 commits.

**feature2: <br />**
Commits: Add maxAttempts constant and game over state. Implement max attempts logic and game over condition. <br />
Branches from dev with 2 commits. Dev branched from main.

**feature3: <br />**
Commits: started hint. got it done. had to fix. done. <br />
Branches from main with 4 commits.

**hotfix: <br />**
Commits: Fix randomInt to properly include max value in range <br />
Branches from main with 1 commit.

Learning Summary:
----------------------------------------------
**Differences between merge, rebase, squash, and cherry-pick: <br />**

Merge is used to combine the commit histories of two branches into one, preserving the history of both the branches.
Merge is great for a collaborative workflow where it is important to have the history of all previous commits. <br />
Rebase is used to re-apply all the commits from one branch on top of another branch.
It is great for keeping the history of commits linear, however it does rewrite the commit history, meaning some information such as what branch the code is coming from is lost.
This makes rebasing unsuitable for collaborative development and it should only be used locally because it will modify the commit history which could affect other developers. <br />
Squash is used to combine multiple commits into a single commit.
Squash, like rebasing, rewrites the commit history, meaning it should only be used locally. <br /> 
Cherry-picking copies a specific commit from one branch and applies it to another branch.
This is good for pulling a specific bug fix into a branch without having to merge the entire branch.

**What you observed in the git history for feature1 vs feature2 vs feature3 <br />**

**feature1:** Feature1 initially branched from the main initial commit with 4 additional commits.
Currrently, the git history is unviewable for feature1 because we deleted the branch. <br />
**feature2:** Feature2 history initially branched from dev with 2 commits.
Currently, the entire commit history of feature2 is viewable, however all of the commits included in feature2 are now linearly included in dev as well.
This is because we rebased feature2 onto dev, rewriting it's commit history to include that of feature2. <br />
**feature3:** Feature3 initially branched from main with 4 (very messy) commits.
Currently, all of the previous commits are unviewable as they were squashed into one, more detailed commit.
This updated commit, along with a few other build configuration changes, are still viewable in feature3.
All of the commit history for feature3 is also included in the dev commit history because we also rebased that branch onto dev.

**When you would use each strategy in real projects <br />**

**Merge:** We would use merge in a project when the team wants to integrate a feature into main or dev while preserving the commit history.
It is great for collaborative work where several developers may be working on the same branch simultaneously because it avoids rewriting other developers' commit history. <br />
**Rebase:** We would use rebase in a project when we want to combine local branches to avoid a messy commit history before we merge the combined branch onto main.
We would NOT directly rebase onto main or dev (or any shared branches) because we would rewrite the commit history for branches that other developers may be basing their work on. <br />
**Squash:** We would use squash in a project when we have local branches which we want to rewrite the commit history for.
We would do this to either clean up messy commit messages or combine several small commits into a larger one before merging this local branch onto dev/main.
Like rebase, we do not want to squash any shared branches. <br />
**Cherry-pick:** We would use cherry-pick when we need to apply a specific commit to a branch without merging the entire branch.
We would do this if there is a system-breaking bug in main that needs to be immediately fixed but we don't want to pull in unfinished features from the branch.
