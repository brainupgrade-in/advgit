# Scenario: Reverting a Commit

Imagine you are working on a project, and a commit was made to the `main` branch that introduced a bug or undesired changes. You need to revert this specific commit without altering the commit history.

### Initial Setup:

#### `main` branch:
- The `main` branch has the following commit history:
  ```sh
  commit ghi9012: Introduce bug
  commit def5678: Add new feature
  commit abc1234: Initial commit
  ```

### Your Challenge:

1. **Identify the commit that introduced the bug (`ghi9012`).**
2. **Revert this specific commit to undo its changes.**

### Detailed Steps:

#### Step 1: Identify the Commit to Revert

1. **View the commit history of the `main` branch**:
   ```sh
   git log --oneline
   ```
   This should show:
   ```sh
   ghi9012 Introduce bug
   def5678 Add new feature
   abc1234 Initial commit
   ```

   The commit `ghi9012` is the one we want to revert.

#### Step 2: Revert the Specific Commit

1. **Ensure you are on the `main` branch**:
   ```sh
   git checkout main
   ```

2. **Revert the specific commit**:
   ```sh
   git revert ghi9012
   ```

   This command creates a new commit that undoes the changes introduced by `ghi9012`. If there are no conflicts, Git will open your default text editor to allow you to edit the commit message for the revert.

3. **Edit the commit message** (if needed), save, and close the editor.

4. **Push the changes to the remote `main` branch**:
   ```sh
   git push origin main
   ```

### Example:

#### Before Reverting:

- **`main` branch**:
  ```sh
  commit ghi9012: Introduce bug
  commit def5678: Add new feature
  commit abc1234: Initial commit
  ```

#### After Reverting `ghi9012`:

- **`main` branch**:
  ```sh
  commit jkl3456: Revert "Introduce bug"
  commit ghi9012: Introduce bug
  commit def5678: Add new feature
  commit abc1234: Initial commit
  ```

### Detailed Explanation:

#### Step-by-Step Reverting:

1. **Identify the Commit**:
   - The commit `ghi9012` that introduced the bug is identified.

2. **Revert the Commit**:
   - Switch to the `main` branch and use `git revert ghi9012` to create a new commit that undoes the changes introduced by `ghi9012`.

3. **Commit Message**:
   - Git will open your default text editor to allow you to edit the commit message for the revert. By default, it will include a message like "Revert 'Introduce bug'".

4. **Push the Changes**:
   - Push the new commit to the remote repository to ensure the changes are reflected there.

### Important Points:

- **Reverting** vs. **Resetting**:
  - `git revert` creates a new commit that undoes the changes of a specific commit. It is safe to use on public branches as it doesn't rewrite history.
  - `git reset` moves the branch pointer backward and can alter commit history, which is not recommended for public branches.

- **Conflict Resolution**:
  - If there are conflicts during the revert, Git will pause and notify you to resolve them. After resolving, stage the resolved files and continue the revert process:
    ```sh
    git add <resolved-files>
    git revert --continue
    ```

### Conclusion:

This scenario demonstrates how to use `git revert` to undo changes introduced by a specific commit without altering the commit history. This is useful for safely undoing changes in a way that is visible and traceable in the commit history.
