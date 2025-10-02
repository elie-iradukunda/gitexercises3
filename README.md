# Git Exercises 3

This repository contains exercises for refining Git history, including committing, amending, rebasing, cherry-picking, and using reflog.

---

## 1. Create Dummy Files

```bash
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ touch test{1..4}.md

2. Initial Commits
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git add test1.md
$ git commit -m "chore: Create initial file"
[dev 333926e] chore: Create initial file
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test3.md

user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git add test2.md
$ git commit -m "chore: Create second file"
# note: test4.md is still untracked

user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git add test4.md
$ git commit -m "chore: Create fourth file"
[dev 776bfab] chore: Create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md


 3. Amend and Refine Commits
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git reset --soft HEAD~1
$ git add test1.md
$ git commit -m "chore: Create first file"

user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git add test4.md
$ git commit --amend -m "chore: Create fourth file"


4. Interactive Rebase
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git rebase -i HEAD~3


Rebased and cleaned up commit messages.

Squashed commits where necessary:

$ git commit --amend -m "chore: Create third and fourth files"



5. Splitting Commits
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git reset HEAD~1
$ git add test1.md
$ git commit -m "chore: Create initial file"
$ git add test2.md
$ git commit -m "chore: Create second file"
$ git add test3.md
$ git commit -m "chore: Create third file"
$ git add test4.md
$ git commit -m "chore: Create fourth file"

user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git rebase -i HEAD~4



6. Dropping Unwanted Commits
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ touch unwanted.txt
$ git add unwanted.txt
$ git commit -m "Unwanted commit"
$ git rebase -i HEAD~4


Removed unwanted commits interactively.

7. Cherry-Picking from Feature Branch
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git checkout -b ft/branch
$ touch test5.md
$ git add test5.md
$ git commit -m "Implemented test 5"
$ git checkout dev
$ git cherry-pick eb38cec


Applied changes from ft/branch into dev.

8. Viewing Logs and History
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev)
$ git log --oneline --graph --all --decorate


Visualized full commit history including all branches.

9. Using Reflog
user@LAPTOP-V9PT987N MINGW64 ~/Desktop/part3/gitexercises3 (dev|CHERRY-PICKING)
$ git reflog
$ git checkout HEAD@{2}
$ git checkout dev