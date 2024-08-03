# Scenario: Stashing Changes to Switch Branches

Imagine you are working on a feature branch (`feature-z`) and have some changes that are not yet ready to be committed. Suddenly, you need to switch to the `main` branch to address a critical bug. You don't want to commit your incomplete work on `feature-z`, so you decide to stash your changes.

#### Initial Setup:

- You are on the `feature-z` branch with uncommitted changes in `app.py`.

```sh
# app.py
def main():
    print("Hello from main")

def feature_z():
    print("Hello from feature Z")
```

- You modify `app.py` to include some new work that isn't ready for commit:

```sh
# app.py
def main():
    print("Hello from main")

def feature_z():
    print("Hello from feature Z")

def incomplete_work():
    print("This work is not yet complete")
```

### Your Challenge:

1. **Stash the uncommitted changes**.
2. **Switch to the `main` branch and address the critical bug**.
3. **Commit the bug fix**.
4. **Return to the `feature-z` branch and apply the stashed changes**.

### Detailed Steps:

#### Step 1: Stash the Uncommitted Changes

1. **View the current status to confirm uncommitted changes**:
   ```sh
   git status
   ```

   You should see that `app.py` has been modified but not yet committed.

2. **Stash the changes**:
   ```sh
   git stash
   ```

   This command saves your local modifications away and reverts the working directory to match the HEAD commit. You will see a message like:
   ```sh
   Saved working directory and index state WIP on feature-z: <commit-hash> <commit-message>
   ```

3. **Verify that the working directory is clean**:
   ```sh
   git status
   ```
   Your working directory should be clean, indicating that the changes have been stashed.

#### Step 2: Switch to the `main` Branch and Address the Bug

1. **Switch to the `main` branch**:
   ```sh
   git checkout main
   ```

2. **Fix the critical bug in `main` branch**:
   Open `app.py` and make the necessary bug fix. For example:

```sh
# app.py
def main():
    print("Hello from main - critical bug fixed")
```

3. **Commit the bug fix**:
   ```sh
   git add app.py
   git commit -m "Fix critical bug in main"
   ```

#### Step 3: Return to the `feature-z` Branch and Apply the Stashed Changes

1. **Switch back to the `feature-z` branch**:
   ```sh
   git checkout feature-z
   ```

2. **Apply the stashed changes**:
   ```sh
   git stash apply
   ```

   This command restores the stashed changes to your working directory.

3. **Verify the changes**:
   Open `app.py` and ensure your incomplete work is back in place.

   ```sh
   # app.py
   def main():
       print("Hello from main")

   def feature_z():
       print("Hello from feature Z")

   def incomplete_work():
       print("This work is not yet complete")
   ```

4. **Optional: Drop the stash**:
   If you are sure you no longer need the stash, you can drop it to clean up:

   ```sh
   git stash drop
   ```

   This removes the stash entry from the stash list.

### Solution Verification:

To verify that the challenge was solved correctly, the following criteria should be met:
- The critical bug fix is committed to the `main` branch.
- The stashed changes are successfully reapplied to the `feature-z` branch.
- The working directory on `feature-z` includes the incomplete / uncommitted work.

### Detailed Explanation:

#### Before Stashing:
- `feature-z` branch with uncommitted changes in `app.py`.

#### After Stashing:
- The working directory is clean, and changes are stashed.

#### After Switching and Fixing the Bug:
- The `main` branch has the bug fix committed.

#### After Applying the Stash:
- `feature-z` branch has the stashed changes reapplied.

### Conclusion:

This scenario demonstrates how to use `git stash` to temporarily save your work, allowing you to switch contexts without committing incomplete changes. This is especially useful when you need to address urgent issues on other branches and then return to your original work seamlessly.
