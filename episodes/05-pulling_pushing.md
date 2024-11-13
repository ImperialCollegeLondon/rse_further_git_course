---
title: "Pulling and Pushing"
teaching: 10
exercises: 5
questions:
- "How do I keep my local branches in sync with the remote branches?"
- "What is the difference between forking and branching?"
objectives:
- Push changes to a remote repository.
- Pull changes from a remote repository.
keypoints:
- With `git push` you can push any committed changes in your current branch to its upstream branch.
- If the current branch has no upstream yet, you can configure one by doing `git push -u origin BRANCH_NAME`.
- Using `git pull` will bring changes in the upstream branch to the local branch.
---

## Multiple branches in remotes

The same way you might have different branches in your local repository, you could
manage different branches in your remote - the same branches or different ones.

As a reminder, remote and local repositories are not automatically synchronised, but
rather it is a manual process done via `git pull` and `git push` commands. This
synchronisation needs to be done **branch by branch** with all of those you want to keep
in sync.

### Pushing

* Its basic use is to synchronise **any committed changes** in your current
 branch to its upstream branch: `git push`.
* Changes in the staging area will not be synchronised.
![Git collaborative]({{ site.baseurl }}/fig/push.png "Push a branch
."){:class="img-responsive"}
* If the current branch has no upstream yet, you can configure one by doing
`git push -u origin BRANCH_NAME`, as done with `main` in the exercise
 above.
![Git collaborative]({{ site.baseurl }}/fig/push_u.png "Push a branch without
 upstream yet."){:class="img-responsive"}
* `push` only operates on your current branch. If you want to push another
 branch, you have to `checkout` that branch first.
* If the upstream branch has changes you do not have in the local branch, the
 command will fail, requesting you to pull those changes first.

Let's try to push changes to the `main` branch. First make sure you are on the `main` branch.

```sh
git switch main
```
{: .commands}
```
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 6 commits.
  (use "git push" to publish your local commits)
```
{: .output}

Notice that git is suggesting you to use `git push` to publish your local commits. Let's do that:

```sh
git push
```
{: .commands}
```
Enumerating objects: 21, done.
Counting objects: 100% (21/21), done.
Delta compression using up to 8 threads
Compressing objects: 100% (18/18), done.
Writing objects: 100% (18/18), 1.83 KiB | 938.00 KiB/s, done.
Total 18 (delta 4), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (4/4), completed with 1 local object.
To https://github.com/username/recipe.git
   57d4505..d10e1e9  main -> main
```
{: .output}

## Pulling

* Opposite to `push`, `pull` brings changes in the upstream branch to the local branch.
* You can check if there are any changes to synchronise in the upstream branch by
  running `git fetch`, which only checks if there are changes, and then `git status` to
  see how your local and remote branch compare in terms of commit history.
* It's best to make sure your repository is in a clean state with no staged or unstaged
  changes.
* If the local and upstream branches have diverged - have different commit history - the
  command will attempt to merge both. If there are conflicts, you will need deal with
  them in the same way described above.
* You can get a new branch existing only in `origin` directly with `git switch
  BRANCH_NAME` without the need of creating the branch locally and then pulling the
  remote.

![Git collaborative]({{ site.baseurl }}/fig/pull.png "Pull remote changes")
{:class="img-responsive"}

{% include links.md %}
