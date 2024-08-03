# Scenario: Applying a Specific Commit to Another Branch

Imagine you are working on a project with the following branches:
- `main`: The main branch containing production-ready code.
- `feature-y`: A feature branch where new features are being developed.

A useful commit has been made on the `feature-y` branch that fixes a minor bug, and you want to apply this specific bug fix to the `main` branch without merging the entire feature branch.

### Initial Setup:

#### `main` branch:
- The `main` branch has the following commit history:
  ```sh
  commit abc1234: Initial commit
  ```

#### `feature-y` branch:
- The `feature-y` branch has the following commit history:
  ```sh
  commit def5678: Fix minor bug in config.py
  commit ghi9012: Add new feature
  commit abc1234: Initial commit
  ```

### Your Challenge:

1. **Identify the commit that fixes the minor bug on the `feature-y` branch.**
2. **Cherry-pick this commit onto the `main` branch.**

### Detailed Steps:

#### Step 1: Identify the Commit to Cherry-Pick

1. **Checkout the `feature-y` branch and view its commit history**:
   ```sh
   git checkout feature-y
   git log --oneline
   ```
   This should show:
   ```sh
   def5678 Fix minor bug in config.py
   ghi9012 Add new feature
   abc1234 Initial commit
   ```

   The commit `def5678` is the one we want to cherry-pick onto the `main` branch.

#### Step 2: Cherry-Pick the Commit onto the `main` Branch

1. **Checkout the `main` branch**:
   ```sh
   git checkout main
   ```

2. **Cherry-pick the specific commit**:
   ```sh
   git cherry-pick def5678
   ```

   This command applies the changes from commit `def5678` on the `main` branch. If there are no conflicts, the commit will be applied directly.

3. **Push the changes to the remote `main` branch** (if needed):
   ```sh
   git push origin main
   ```

### Possible Outcomes:

1. **Successful Cherry-Pick**:
   - The commit is applied to the `main` branch without any conflicts.

2. **Conflicts**:
   - If there are conflicts, Git will pause and notify you. You will need to resolve the conflicts, stage the resolved files, and continue the cherry-pick process.

### Example:

#### Before Cherry-Picking:

- **`main` branch**:
  ```sh
  commit abc1234: Initial commit
  ```

- **`feature-y` branch**:
  ```sh
  commit def5678: Fix minor bug in config.py
  commit ghi9012: Add new feature
  commit abc1234: Initial commit
  ```

#### After Cherry-Picking `def5678` onto `main`:

- **`main` branch**:
  ```sh
  commit jkl3456: Fix minor bug in config.py (cherry-picked from def5678)
  commit abc1234: Initial commit
  ```

### Detailed Explanation:

#### Step-by-Step Cherry-Picking:

1. **Identify the Commit**:
   - The commit `def5678` is identified on `feature-y`.

2. **Checkout `main` and Cherry-Pick**:
   - Switch to `main` and apply the changes from `def5678`.

3. **Resolve Conflicts** (if any):
   - Git will prompt you to resolve conflicts if they occur. After resolving, stage the resolved files:
     ```sh
     git add <resolved-files>
     git cherry-pick --continue
     ```

### Conclusion:

This scenario demonstrates how to use `git cherry-pick` to apply a specific commit from one branch to another. This is particularly useful when you want to apply a specific fix or feature without merging the entire branch, allowing for more granular control over the changes in your branches.
