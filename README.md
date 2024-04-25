# Git Assignment - stumac 

## a. What is an _issue_?
An issue is a possible bug, enhancement request, or something that otherwise requires the attention of the developer. In github, they're found under `https://github.com/<organization_or_user>/<repository>/issues`. They usually contain a title/subject, a description of the problem/feature request, and allow for discussions in a thread based style of conversation.

## b. What is a _pull request_?
A pull request is a request to merge code in a branch (or fork!) into another branch. By creating this "PR", github generates a "diff" of the code between the two branches, indicating what code has been removed, added, or changed. It allows for other developers to review, approve, request changes, or question/comment on the changeset. Once the required number of approvals (depending on organization), the changeset can be merged into the base branch. Github allows multiple ways to merge the changeset (it notably lacks the `fast-forward` option though)

## c. How do I open up a _pull request_?

1. Go to the repository in question and click "Pull Requests" (or go to `github.com/<org>/<repository/pulls`).
2. Click on New Pull Request.
3. Select the "base" branch. This is the branch that you want your code to be merged into.
4. Select the branch you want to merge in `compare`.
5. Click "Create Pull Request" button
6. Input a subject and description in the provided fields. (details of the description/subject vary by organization).
7. Click on "Create Pull Request".

## d. Give me a step by step guide on how to add someone to your repository.
1. Go to your repository.
2. Go to "settings".
3. Go to "collaborators.
4. Select "Add People".
5. Enter the github handles of the user/team you want to add.
6. Click "Add username to this repository".

## e. What is the difference between `git` and `GitHub`?
Git is a gool that tracks changesets and versions source code. Github is a "Software as a Service" that allows developers to manage software projects using Git, with keeping Github as the server or "source of truth" for the project.

## f. What does `git diff` do?
Using `git diff` without any modifiers will compare the current "working tree" to the most previous commit that the working tree is based off of. Therefore, if you're on a feature branch, it will compare the changes you've made to the files since your last commit, and show the differences between the two.

i.e: 
```diff
diff --git a/README.md b/README.md
index e69de29..66d4cda 100644
--- a/README.md
+++ b/README.md
@@ -0,0 +1,37 @@
+# Git Assignment - stumac
+
+
e
+
+## a. What is an _issue_?
```
with the `+` signs being what was added (in which case, from diff source b, the working tree)
It is possible diff between branches, or commits as well. I.e: To compare branches: `git diff <base_branch> <changeset branch>`.

## g. What is the `main` branch?
the main branch is a common convention used by the git community that can be considered the "default" or "base" branch. It is generally considered to be the branch that is the "source of truth" for the software project. Depending on the merge flow used, this branch may be branched off of for feature/bugfix branches, or can be considered a historical record or previous released of the software (i.e: Git-flow)

## h. Besides our initial commit if it is a new repository, should we directly push our changes directly into the `main` branch?
Generally speaking, no. If the main branch is the source of truth, any changes to it usually require a certain level of scrutiny from other developers. Additionally, with many projects, other tools rely on PRs and merges to kick off other jobs. As such, if for some reason you are able to commit to main directly, you run the risk of your code not being tested, deployed, or otherwise working its way through the organization's pipeline. 
