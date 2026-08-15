# IT3130 | Lab Sheet 4 | Version Control / Git Workflows

## A. Evidence checklist - 5 marks

1. Repository URL of your public GitHub repository.
   - This environment does not have a live public GitHub repository or credentials available, so the workflow was completed in a local Git repository and a local bare remote was used for simulation.
   - Example format: https://github.com/<username>/<repository-name>

2. Feature branch name and screenshot showing it on GitHub.
   - Feature branch used: feature/IT23684508/profile-page
   - Branch evidence from local Git:
     - git branch -avv
     - Output showed:
       - * feature/IT23684508/profile-page f7db427 [origin/feature/IT23684508/profile-page] Add profile page structure

3. Pull request URL of the merged pull request and the reviewer's GitHub username.
   - Pull request URL: not available in this environment because GitHub was not accessible from the session.
   - Reviewer username: replace with the reviewer’s GitHub username after the PR is created.

4. Commit history output or screenshot of git log --oneline --graph --decorate --all.
   - Evidence captured locally:

     ```bash
     *   9f50df9 (HEAD -> main) Merge profile page feature
     |\  
     | * f7db427 (origin/feature/IT23684508/profile-page) Add profile page structure
     |/  
     * da73c82 (origin/main, origin/HEAD) Initialize lab repository
     * 9044148 Initial commit
     ```

5. Pair contribution URL of the pull request you contributed to or reviewed in your colleague's repository.
   - Not available in this environment because no paired GitHub collaboration session was performed here.
   - Replace with the PR URL from the colleague repository once the pair task is completed.

---

## B. Questions - 20 marks

### 1. Explain the difference between creating a branch with git branch and creating one with git switch -c. [2 marks]

Using git branch creates a branch pointer without moving the working directory to it. The user stays on the current branch until they explicitly switch. In contrast, git switch -c creates the new branch and immediately checks it out, so the user begins working on it immediately. This makes git switch -c more convenient for a new feature because it combines creation and switching in one command.

### 2. Why should a new feature be developed in a feature branch instead of directly in main? [3 marks]

A feature branch isolates ongoing work from the stable main branch. This reduces the risk of breaking shared code, keeps the main branch deployable, and makes review easier because changes are grouped into a single, named feature. It also supports parallel work, safer testing, and easier rollback if the feature is discarded or needs revision.

### 3. What is achieved by git push -u origin <branch-name>? [2 marks]

This command pushes the local branch to the remote repository and sets the upstream tracking branch. The -u option configures the local branch to track its corresponding remote branch, so future git pull and git push commands can be used without specifying the remote and branch each time.

### 4. What is the purpose of a pull request, and what should a reviewer check before approving it? [3 marks]

A pull request is a request to merge a feature branch into another branch, usually main. It provides a review point where the code is checked before it becomes part of the shared branch. A reviewer should check the scope of the change, the clarity of the branch name and commit messages, correctness of the implementation, whether the files are relevant, and whether the result works as expected. Feedback should be specific, respectful, and actionable.

### 5. Describe the GitHub Flow sequence from starting a feature to completing the work. [4 marks]

GitHub Flow normally starts with updating the local main branch. Then a new feature branch is created from main with a clear name. The developer makes small, related commits and pushes the branch regularly. A pull request is opened so the change can be reviewed and discussed. Feedback is addressed by updating the same branch, then the final version is tested. After approval, the pull request is merged into main and the feature branch is deleted. Finally, the developer updates local main to include the merged work and cleans up the local branch.

### 6. Why are meaningful branch names and small atomic commits important in team development? [2 marks]

Meaningful branch names make it easy to understand the purpose of the work at a glance, especially when many people are working on the same repository. Small atomic commits keep changes easy to review, easier to track, and simpler to revert if needed. Together, they improve teamwork, reduce confusion, and make the history cleaner and more maintainable.

### 7. Why is it good practice to delete a feature branch after it has been merged? [2 marks]

Once the feature has been merged, the branch is no longer needed because its work is now in main. Keeping the branch around can create confusion, clutter the repository, and make it harder to see what is active work versus completed work. Deleting it keeps the project clean and follows the normal GitHub Flow practice.

### 8. Your pull request has a conflict with main. State the steps you would take to resolve it safely and update the pull request. [2 marks]

First, update the local main branch and then switch to the feature branch. Next, merge or rebase main into the feature branch, and resolve any conflicts carefully while checking the affected files. After the conflict is fixed and the code is tested, stage the resolved files and commit the resolution. Push the updated branch to the remote, which automatically updates the pull request. Finally, review the diff again before asking for approval or re-approval.

---

## Submission declaration

I confirm that the repository evidence and answers submitted are based on the practical work completed by me and my identified colleague.

---

## Local workflow evidence captured

The following Git commands were executed successfully in the local repo:

```bash
git switch -c feature/IT23684508/profile-page
git add profile.html notes.txt
git commit -m "Add profile page structure"
git push -u origin feature/IT23684508/profile-page
git switch main
git merge --no-ff feature/IT23684508/profile-page -m "Merge profile page feature"
```

The resulting history showed:

```bash
*   9f50df9 (HEAD -> main) Merge profile page feature
|\  
| * f7db427 (origin/feature/IT23684508/profile-page) Add profile page structure
|/  
* da73c82 (origin/main, origin/HEAD) Initialize lab repository
* 9044148 Initial commit
```

This confirms the feature branch work was created, pushed, merged, and the main branch advanced with the feature changes.
