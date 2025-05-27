# Git Collaboration Reflection

## What was the most challenging Git concept this week?

The most challenging concept was **Git rebase**. It was a bit confusing at first because it seems similar to `git merge`, but the internal behavior and effect on commit history are quite different.

---

## What did you learn about collaboration?

Through collaboration, we discovered that each team member had different approaches to completing tasks or explaining commands.

For example:
- Some preferred using `nano` instead of `vim` for editing files.
- Others used `git switch` instead of `git checkout`.

This experience highlighted the benefit of collaboration — we learned new tools, shortcuts, and different ways to solve the same problems more efficiently.

---

## What mistakes did you make, and how did you fix them?

We attempted to create a merge conflict using `git rebase` to understand how Git handles conflicts during rebasing.

At first, we made changes to `conflict.txt` only on the `main` branch. Then we switched to `feature-a` and ran:

```bash
git rebase main
```

However, no conflict occurred — which confused us.

Why no conflict happened:
Git only raises a conflict during a rebase if both branches modify the same lines in the same file.
In our case, feature-a didn’t change that part of the file, so Git was able to reapply the commits without any issues.

Later, we modified the same lines in conflict.txt on both branches. When we rebased feature-a onto main, Git detected a conflict, which is what we expected.