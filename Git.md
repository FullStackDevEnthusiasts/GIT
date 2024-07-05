1. What is Git, and how is it different from other version control systems?
   - Git is a distributed version control system.
   - Unlike centralized systems, every user has a full copy of the repository.
   - Git allows offline work and commits.
   - It uses SHA-1 hashes for integrity.
   - Branching and merging are easier and more efficient in Git.

2. Explain the difference between `git pull` and `git fetch`.
   - `git fetch` updates local repository with remote changes without merging.
   - `git pull` does both fetch and merge.
   - `git pull` can cause conflicts if local changes are not committed.
   - `git fetch` allows reviewing changes before merging.
   - `git pull` is riskier in large, active projects.

3. How do you create a new branch in Git?
   - Use `git branch branch_name` to create a new branch.
   - Switch to the branch with `git checkout branch_name`.
   - Alternatively, create and switch with `git checkout -b branch_name`.
   - Branches are lightweight pointers.
   - Useful for working on features or fixes in isolation.

4. What is a merge conflict, and how do you resolve it?
   - A conflict occurs when changes in different branches clash.
   - Git marks the conflict in the files.
   - Use `git status` to identify conflicted files.
   - Edit the files to resolve conflicts.
   - Use `git add` to mark as resolved, then commit.

5. How can you revert a commit in Git?
   - Use `git revert commit_hash` to create a new commit that undoes changes.
   - Keeps history intact.
   - Alternatively, use `git reset` to undo changes without keeping history.
   - `git reset --hard` discards all changes.
   - `git reset --soft` keeps changes in the working directory.

6. Explain the difference between `git clone` and `git fork`.
   - `git clone` creates a local copy of a repository.
   - Forking is typically done on platforms like GitHub to create a personal copy.
   - Cloning is done via `git clone repository_url`.
   - Forking allows you to contribute back to the original repository.
   - Forks are usually remote repositories.

7. What is the purpose of `git stash`?
   - Temporarily saves changes not ready to be committed.
   - Use `git stash` to save and `git stash apply` to retrieve.
   - Useful when you need to switch branches quickly.
   - `git stash pop` applies and removes the stash.
   - `git stash list` shows stashed changes.

8. How do you remove a file from the Git repository but keep it locally?
   - Use `git rm --cached file_name`.
   - Removes from the repository index.
   - Keeps the file in the working directory.
   - Useful for sensitive or large files.
   - Commit the changes to update the repository.

9. What is a Git hook, and how is it used?
   - Scripts that run at specific points in Git's lifecycle.
   - Examples include pre-commit, post-commit, pre-push.
   - Used for enforcing policies, running tests, or notifications.
   - Hooks are stored in the `.git/hooks` directory.
   - They are local to the repository and not shared.

10. How do you see the commit history in Git?
    - Use `git log` to view the history.
    - `git log --oneline` shows a simplified view.
    - `git log -p` shows changes introduced by each commit.
    - `git log --graph` shows a visual representation of branches.
    - Filters like `--author`, `--since`, and `--until` refine the history.

11. What is the difference between `git reset` and `git revert`?
    - `git reset` undoes changes by moving the HEAD.
    - `git revert` creates a new commit that undoes changes.
    - `git reset --soft` keeps changes staged.
    - `git reset --hard` discards all changes.
    - `git revert` is safer as it preserves history.

12. How do you configure a Git repository to ignore certain files?
    - Use a `.gitignore` file.
    - List patterns of files to ignore.
    - Common entries include `*.log`, `node_modules/`.
    - Git respects `.gitignore` in the root and subdirectories.
    - Use `git check-ignore -v file_name` to debug.

13. Explain the purpose of `git rebase`.
    - Integrates changes from one branch to another.
    - Re-applies commits on top of another base.
    - Creates a cleaner, linear history.
    - Can be used interactively with `git rebase -i`.
    - Risk of conflicts; use with caution.

14. What is `git cherry-pick`?
    - Applies changes from a specific commit to the current branch.
    - Use `git cherry-pick commit_hash`.
    - Useful for backporting bug fixes.
    - Keeps original commit metadata.
    - Can cause conflicts if changes overlap.

15. How do you rename a branch in Git?
    - Switch to the branch to rename: `git checkout old_branch`.
    - Use `git branch -m new_branch`.
    - Updates the branch name locally.
    - Push the renamed branch: `git push origin new_branch`.
    - Delete the old branch on the remote: `git push origin --delete old_branch`.

16. What is the function of `git diff`?
    - Shows differences between commits, branches, or working directory.
    - Use `git diff` for unstaged changes.
    - `git diff --staged` shows staged changes.
    - Compare branches: `git diff branch1 branch2`.
    - `git diff commit1 commit2` shows differences between commits.

17. How do you squash commits in Git?
    - Use interactive rebase: `git rebase -i HEAD~n`.
    - Mark commits to squash with `s` or `squash`.
    - Squashed commits combine into a single commit.
    - Useful for cleaning up commit history.
    - Can edit commit message during the process.

18. How do you handle large files in Git repositories?
    - Use Git Large File Storage (LFS).
    - Install Git LFS and track files: `git lfs track "file_pattern"`.
    - LFS stores large files outside the repository.
    - Reduces repository size and improves performance.
    - LFS objects are fetched only when needed.

19. What are Git submodules, and how are they used?
    - Repositories within a repository.
    - Use `git submodule add repository_url path` to add.
    - Useful for managing dependencies.
    - Update submodules with `git submodule update --remote`.
    - Changes to submodules need separate commits.

20. How do you undo the last commit without losing changes?
    - Use `git reset --soft HEAD~1`.
    - Moves HEAD to the previous commit.
    - Keeps changes in the staging area.
    - Useful for correcting recent commits.
    - Commit again after making necessary changes.
   
21. How do you check the status of your working directory and staging area in Git?
    - Use `git status`.
    - Shows modified files.
    - Indicates files staged for commit.
    - Lists untracked files.
    - Provides hints for next steps.

22. What is the use of `git tag` and how do you create one?
    - Tags are used to mark specific points in history.
    - Create an annotated tag: `git tag -a v1.0 -m "version 1.0"`.
    - Lightweight tags: `git tag v1.0`.
    - List tags with `git tag`.
    - Push tags to remote: `git push origin v1.0`.

23. How do you undo changes in your working directory?
    - Use `git checkout -- file_name` to discard changes.
    - Reverts file to last committed state.
    - Use `git restore file_name` in newer Git versions.
    - Can also discard all changes: `git checkout .`.
    - Be cautious as changes cannot be recovered.

24. What is the `HEAD` in Git?
    - `HEAD` points to the current branch's latest commit.
    - Detached `HEAD` occurs when checking out a specific commit.
    - Commands like `git reset`, `git checkout` modify `HEAD`.
    - `HEAD~1` references the parent commit.
    - Understanding `HEAD` is crucial for branch navigation.

25. Explain the concept of a detached `HEAD`.
    - Occurs when checking out a specific commit, not a branch.
    - Changes are not associated with a branch.
    - Use `git checkout branch_name` to reattach `HEAD`.
    - Can create a new branch from a detached state: `git checkout -b new_branch`.
    - Allows experimentation without affecting branches.

26. How do you remove a remote branch in Git?
    - Use `git push origin --delete branch_name`.
    - Removes the branch from the remote repository.
    - Ensure no one is using the branch before deletion.
    - Local branch remains unaffected.
    - Useful for cleaning up stale branches.

27. What is `git bisect` and how is it used?
    - Used for debugging to find commit that introduced a bug.
    - Start with `git bisect start`.
    - Mark good and bad commits with `git bisect good` and `git bisect bad`.
    - Git performs a binary search to find the offending commit.
    - Helps in pinpointing problematic changes efficiently.

28. How do you list all branches in a Git repository?
    - Use `git branch` for local branches.
    - `git branch -r` lists remote branches.
    - `git branch -a` lists both local and remote branches.
    - Current branch is marked with an asterisk.
    - Helps in managing multiple branches.

29. How do you configure a Git repository with a specific user name and email?
    - Use `git config user.name "Your Name"` for the name.
    - Use `git config user.email "your.email@example.com"` for the email.
    - Configuration can be global with `--global` flag.
    - Local configuration affects only the current repository.
    - Important for tracking contributions.

30. What is the purpose of `git blame`?
    - Shows author and commit information for each line in a file.
    - Use `git blame file_name`.
    - Helps identify who made specific changes.
    - Useful for understanding code history.
    - Can specify a range with `git blame commit_hash file_name`.

31. How do you rename a file in Git?
    - Use `git mv old_file_name new_file_name`.
    - Stages the rename for commit.
    - Alternatively, rename manually and use `git add`.
    - Commit the changes to update the repository.
    - Preserves file history.

32. How do you initialize a new Git repository?
    - Use `git init` in the project directory.
    - Creates a new `.git` subdirectory.
    - Initializes an empty repository.
    - Track files with `git add`.
    - Commit changes with `git commit`.

33. Explain the purpose of `git remote`.
    - Manages set of tracked repositories.
    - Use `git remote add name url` to add a remote.
    - List remotes with `git remote -v`.
    - Remove a remote with `git remote remove name`.
    - Useful for collaborating with others.

34. How do you handle commit messages in Git?
    - Use `git commit -m "message"` for short messages.
    - Use `git commit` to open an editor for longer messages.
    - Follow conventions like imperative mood.
    - First line should be a summary, followed by a blank line and detailed description.
    - Good messages improve project maintainability.

35. How do you reset a file to its state at a specific commit?
    - Use `git checkout commit_hash -- file_name`.
    - Reverts the file to its state at the specified commit.
    - Stages the change for the next commit.
    - Useful for undoing specific file changes.
    - Careful as it can lead to loss of changes.

36. How do you manage multiple remotes in a single Git repository?
    - Add multiple remotes with `git remote add`.
    - Fetch changes from specific remotes with `git fetch remote_name`.
    - Push changes with `git push remote_name branch_name`.
    - Track branches from different remotes.
    - Useful for collaborating across multiple repositories.

37. What is the purpose of `git clean`?
    - Removes untracked files from the working directory.
    - Use `git clean -n` for a dry run.
    - Use `git clean -f` to remove files.
    - `git clean -df` removes untracked directories.
    - Helpful for cleaning up temporary files.

38. How do you view the commit history of a specific file?
    - Use `git log file_name`.
    - Shows commits that modified the file.
    - Combine with `-p` to see changes.
    - Use `--follow` to track across renames.
    - Helps in understanding file evolution.

39. How do you change the last commit message?
    - Use `git commit --amend`.
    - Opens editor to modify the message.
    - Use `-m "new message"` for a direct change.
    - Only affects the latest commit.
    - Useful for correcting typos or adding details.

40. How do you list files changed in a commit?
    - Use `git diff-tree --no-commit-id --name-only -r commit_hash`.
    - Shows names of files changed in the commit.
    - Use `git show --name-only commit_hash` for detailed output.
    - Helps in reviewing changes.
    - Useful for generating release notes.
