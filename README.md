# week4-collaboration




```bash
avichai98@DESKTOP-GG5QEKH:~/week4$ git clone https://github.com/Avichai98/week4-collaboration.git
Cloning into 'week4-collaboration'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.
avichai98@DESKTOP-GG5QEKH:~/week4$ ls
practice  week4-collaboration
avichai98@DESKTOP-GG5QEKH:~/week4$ cd week4-collaboration/
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ ls
README.md
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git checkout -b feature-a
Switched to a new branch 'feature-a'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git checkout -b feature-b
Switched to a new branch 'feature-b'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
On branch feature-b
nothing to commit, working tree clean
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git branch
  feature-a
* feature-b
  main
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ touch conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ echo "Conflict feature-b" > conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt
Conflict feature-b
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add .
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ ls
README.md  conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit -m "Conflict to feature-b"
[feature-b b943010] Conflict to feature-b
 1 file changed, 1 insertion(+)
 create mode 100644 conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch feature-a
Switched to branch 'feature-a'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ ls
README.md
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ echo "Conflict feature-a" > conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ ls
README.md  conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt
Conflict feature-a
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add .
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit -m "Conflict to feature-a"
[feature-a 9cb5c3c] Conflict to feature-a
 1 file changed, 1 insertion(+)
 create mode 100644 conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git merge feature-a
Updating 2f50cbd..9cb5c3c
Fast-forward
 conflict.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ ls
README.md  conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git merge feature-b
Auto-merging conflict.txt
CONFLICT (add/add): Merge conflict in conflict.txt
Automatic merge failed; fix conflicts and then commit the result.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt
<<<<<<< HEAD
Conflict feature-a
=======
Conflict feature-b
>>>>>>> feature-b
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ vim conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-a
+
Conflict feature-b

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both added:      conflict.txt

no changes added to commit (use "git add" and/or "git commit -a")
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit
U       conflict.txt
error: Committing is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit
[main 3724ba4] Merge branch 'feature-b'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch feature-a
Switched to branch 'feature-a'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt
Conflict feature-a
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git rebase main
Successfully rebased and updated refs/heads/feature-a.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-a
+
Conflict feature-b

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ nano conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
On branch feature-a
nothing to commit, working tree clean
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ vim conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit
Aborting commit due to empty commit message.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit -m "updating conflict.txt"
[main eb08b9a] updating conflict.txt
 1 file changed, 1 insertion(+), 3 deletions(-)
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-b + feature-a

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch feature-a
Switched to branch 'feature-a'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-a
+
Conflict feature-b

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git rebase main
Successfully rebased and updated refs/heads/feature-a.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-b + feature-a

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
On branch feature-a
nothing to commit, working tree clean
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ nano conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add
Nothing specified, nothing added.
hint: Maybe you wanted to say 'git add .'?
hint: Turn this message off by running
hint: "git config advice.addEmptyPathspec false"
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add .
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit -m "updated conflict.txt"
[feature-a 1c1ee4a] updated conflict.txt
 1 file changed, 1 insertion(+), 1 deletion(-)
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-b + feature-a + c

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ nano conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add .
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit -m "Updated conflict.txt by main"
[main 60a9f36] Updated conflict.txt by main
 1 file changed, 1 insertion(+), 1 deletion(-)
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-b + feature-a + main

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch feature-a
Switched to branch 'feature-a'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git rebase main
Auto-merging conflict.txt
CONFLICT (content): Merge conflict in conflict.txt
error: could not apply 1c1ee4a... updated conflict.txt
hint: Resolve all conflicts manually, mark them as resolved with
hint: "git add/rm <conflicted_files>", then run "git rebase --continue".
hint: You can instead skip this commit: run "git rebase --skip".
hint: To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply 1c1ee4a... updated conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ vim conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
interactive rebase in progress; onto 60a9f36
Last command done (1 command done):
   pick 1c1ee4a updated conflict.txt
No commands remaining.
You are currently rebasing branch 'feature-a' on '60a9f36'.
  (fix conflicts and then run "git rebase --continue")
  (use "git rebase --skip" to skip this patch)
  (use "git rebase --abort" to check out the original branch)

Unmerged paths:
  (use "git restore --staged <file>..." to unstage)
  (use "git add <file>..." to mark resolution)
        both modified:   conflict.txt

no changes added to commit (use "git add" and/or "git commit -a")
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git rebase --continue
[detached HEAD 82de7be] updated conflict.txt
 1 file changed, 1 insertion(+), 2 deletions(-)
Successfully rebased and updated refs/heads/feature-a.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git log --oneline --graph --all
* 82de7be (HEAD -> feature-a) updated conflict.txt
* 60a9f36 (main) Updated conflict.txt by main
* eb08b9a updating conflict.txt
*   3724ba4 Merge branch 'feature-b'
|\
| * b943010 (feature-b) Conflict to feature-b
* | 9cb5c3c Conflict to feature-a
|/
* 2f50cbd (origin/main, origin/HEAD) Initial commit
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
On branch feature-a
nothing to commit, working tree clean
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git log --oneline  --all
82de7be (HEAD -> feature-a) updated conflict.txt
60a9f36 (main) Updated conflict.txt by main
eb08b9a updating conflict.txt
3724ba4 Merge branch 'feature-b'
9cb5c3c Conflict to feature-a
b943010 (feature-b) Conflict to feature-b
2f50cbd (origin/main, origin/HEAD) Initial commit
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git log  --all
commit 82de7be297a8365e9a594abc55fc281360e0804d (HEAD -> feature-a)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:33:50 2025 +0300

    updated conflict.txt

commit 60a9f3658f6909e63e0c6e189a3be84ecbaf9bd8 (main)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:35:16 2025 +0300

    Updated conflict.txt by main

commit eb08b9adaef0d4c5940473d92542e482ce275a1f
commit 82de7be297a8365e9a594abc55fc281360e0804d (HEAD -> feature-a)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:33:50 2025 +0300

    updated conflict.txt

commit 60a9f3658f6909e63e0c6e189a3be84ecbaf9bd8 (main)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:35:16 2025 +0300

    Updated conflict.txt by main

commit eb08b9adaef0d4c5940473d92542e482ce275a1f
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:26:55 2025 +0300

    updating conflict.txt

commit 3724ba495190a0292a1e390c2257b5b3b7bf908a
Merge: 9cb5c3c b943010
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:11:20 2025 +0300

    Merge branch 'feature-b'

commit 9cb5c3c582b531da71f672cd398d71f466c5c288
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:05:23 2025 +0300

    Conflict to feature-a

commit b943010df2cbb51a09dac2838da447c3fc00c3f9 (feature-b)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:03:57 2025 +0300

    Conflict to feature-b

commit 2f50cbdea8aff8b79dc89f1d35dfe85887dc575e (origin/main, origin/HEAD)
Author: Avichai Shchori <127767873+Avichai98@users.noreply.github.com>
Date:   Tue May 27 09:50:39 2025 +0300

    Initial commit
(END)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:26:55 2025 +0300

    updating conflict.txt

commit 3724ba495190a0292a1e390c2257b5b3b7bf908a
Merge: 9cb5c3c b943010
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:11:20 2025 +0300

    Merge branch 'feature-b'

commit 9cb5c3c582b531da71f672cd398d71f466c5c288
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:05:23 2025 +0300

    Conflict to feature-a

commit b943010df2cbb51a09dac2838da447c3fc00c3f9 (feature-b)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:03:57 2025 +0300

    Conflict to feature-b

commit 2f50cbdea8aff8b79dc89f1d35dfe85887dc575e (origin/main, origin/HEAD)
Author: Avichai Shchori <127767873+Avichai98@users.noreply.github.com>
Date:   Tue May 27 09:50:39 2025 +0300

    Initial commit
(END)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:26:55 2025 +0300

    updating conflict.txt

commit 3724ba495190a0292a1e390c2257b5b3b7bf908a
Merge: 9cb5c3c b943010
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:11:20 2025 +0300

    Merge branch 'feature-b'

commit 9cb5c3c582b531da71f672cd398d71f466c5c288
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:05:23 2025 +0300

    Conflict to feature-a

commit b943010df2cbb51a09dac2838da447c3fc00c3f9 (feature-b)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:03:57 2025 +0300

    Conflict to feature-b

commit 2f50cbdea8aff8b79dc89f1d35dfe85887dc575e (origin/main, origin/HEAD)
Author: Avichai Shchori <127767873+Avichai98@users.noreply.github.com>
Date:   Tue May 27 09:50:39 2025 +0300

    Initial commit

[1]+  Stopped                 git log --all
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git log main
commit 60a9f3658f6909e63e0c6e189a3be84ecbaf9bd8 (main)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:35:16 2025 +0300

    Updated conflict.txt by main

commit eb08b9adaef0d4c5940473d92542e482ce275a1f
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:26:55 2025 +0300

    updating conflict.txt

commit 3724ba495190a0292a1e390c2257b5b3b7bf908a
Merge: 9cb5c3c b943010
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:11:20 2025 +0300

    Merge branch 'feature-b'

commit 9cb5c3c582b531da71f672cd398d71f466c5c288
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:05:23 2025 +0300

    Conflict to feature-a

commit b943010df2cbb51a09dac2838da447c3fc00c3f9 (feature-b)
Author: Avichai <avichai.shchori@gmail.com>
Date:   Tue May 27 10:03:57 2025 +0300


[2]+  Stopped                 git log main
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git log main --oneline
60a9f36 (main) Updated conflict.txt by main
eb08b9a updating conflict.txt
3724ba4 Merge branch 'feature-b'
9cb5c3c Conflict to feature-a
b943010 (feature-b) Conflict to feature-b
2f50cbd (origin/main, origin/HEAD) Initial commit
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt
Conflict feature-b + feature-a + main + c

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-b + feature-a + main

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch feature-b
Switched to branch 'feature-b'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt
Conflict feature-b
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git log --oneline
b943010 (HEAD -> feature-b) Conflict to feature-b
2f50cbd (origin/main, origin/HEAD) Initial commit
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 5 commits.
  (use "git push" to publish your local commits)
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git cherry-pick b943010
Auto-merging conflict.txt
CONFLICT (add/add): Merge conflict in conflict.txt
error: could not apply b943010... Conflict to feature-b
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git cherry-pick --continue".
hint: You can instead skip this commit with "git cherry-pick --skip".
hint: To abort and get back to the state before "git cherry-pick",
hint: run "git cherry-pick --abort".
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ code .
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ cat conflict.txt

Conflict feature-b + feature-a + main

Conflict feature-b
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add conflict.txt
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git cherry-pick --continue
[main 322f2f0] Conflict to feature-b after cherry-pick
 Date: Tue May 27 10:03:57 2025 +0300
 1 file changed, 1 insertion(+)
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
On branch main
Your branch is ahead of 'origin/main' by 6 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push
Username for 'https://github.com': avichai98
Password for 'https://avichai98@github.com':
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/Avichai98/week4-collaboration.git/'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push
Username for 'https://github.com': avichai98
Password for 'https://avichai98@github.com':
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/Avichai98/week4-collaboration.git/'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push
Username for 'https://github.com': Avichai98
Password for 'https://Avichai98@github.com':
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.
fatal: Authentication failed for 'https://github.com/Avichai98/week4-collaboration.git/'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push
Username for 'https://github.com': Avichai98
Password for 'https://Avichai98@github.com':
Enumerating objects: 19, done.
Counting objects: 100% (19/19), done.
Delta compression using up to 16 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (18/18), 1.68 KiB | 1.68 MiB/s, done.
Total 18 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/Avichai98/week4-collaboration.git
   2f50cbd..322f2f0  main -> main
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch feature-a
Switched to branch 'feature-a'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push
fatal: The current branch feature-a has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin feature-a

To have this happen automatically for branches without a tracking
upstream, see 'push.autoSetupRemote' in 'git help config'.

avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git status
On branch feature-a
nothing to commit, working tree clean
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push origin feature-a
Username for 'https://github.com': Avichai98
Password for 'https://Avichai98@github.com':
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 16 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 323 bytes | 323.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'feature-a' on GitHub by visiting:
remote:      https://github.com/Avichai98/week4-collaboration/pull/new/feature-a
remote:
To https://github.com/Avichai98/week4-collaboration.git
 * [new branch]      feature-a -> feature-a
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push --set-upstream origin feature-a
Username for 'https://github.com': Avichai98
Password for 'https://Avichai98@github.com':
branch 'feature-a' set up to track 'origin/feature-a'.
Everything up-to-date
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git switch feature-b
Switched to branch 'feature-b'
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push --set-upstream origin feature-b
Username for 'https://github.com': Avichai98
Password for 'https://Avichai98@github.com':
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'feature-b' on GitHub by visiting:
remote:      https://github.com/Avichai98/week4-collaboration/pull/new/feature-b
remote:
To https://github.com/Avichai98/week4-collaboration.git
 * [new branch]      feature-b -> feature-b
branch 'feature-b' set up to track 'origin/feature-b'.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ code .
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ code .
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add
Nothing specified, nothing added.
hint: Maybe you wanted to say 'git add .'?
hint: Turn this message off by running
hint: "git config advice.addEmptyPathspec false"
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git add .
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit
Aborting commit due to empty commit message.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git commit -m "Adding REFLECTION.md"
[main e4ba0cc] Adding REFLECTION.md
 1 file changed, 37 insertions(+)
 create mode 100644 REFLECTION.md
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push
Username for 'https://github.com': Avichai199
Password for 'https://Avichai199@github.com':
[3]+  Stopped                 git push
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git push
Username for 'https://github.com': Avichai98
Password for 'https://Avichai98@github.com':
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 16 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.08 KiB | 1.08 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/Avichai98/week4-collaboration.git
   322f2f0..e4ba0cc  main -> main
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git pull main
fatal: 'main' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git pull
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 5 (delta 0), reused 5 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (5/5), 737 bytes | 81.00 KiB/s, done.
From https://github.com/Avichai98/week4-collaboration
   e4ba0cc..3f8588d  main       -> origin/main
Updating e4ba0cc..3f8588d
Fast-forward
 .github/js-lint.yml | 25 +++++++++++++++++++++++++
 demo.js             |  4 ++++
 2 files changed, 29 insertions(+)
 create mode 100644 .github/js-lint.yml
 create mode 100644 demo.js
avichai98@DESKTOP-GG5QEKH:~/week4/week4-collaboration$ git pull
remote: Enumerating objects: 20, done.
remote: Counting objects: 100% (20/20), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 17 (delta 4), reused 16 (delta 4), pack-reused 0 (from 0)
Unpacking objects: 100% (17/17), 1.81 KiB | 185.00 KiB/s, done.
From https://github.com/Avichai98/week4-collaboration
   3f8588d..b5abf2f  main       -> origin/main
Updating 3f8588d..b5abf2f
Fast-forward
 .github/{ => workflows}/js-lint.yml | 12 ++++++------
 demo.js                             |  9 ++++++---
 eslint.config.js                    | 10 ++++++++++
 3 files changed, 22 insertions(+), 9 deletions(-)
 rename .github/{ => workflows}/js-lint.yml (56%)
 mode change 100644 => 100755 demo.js
 create mode 100644 eslint.config.js
```
