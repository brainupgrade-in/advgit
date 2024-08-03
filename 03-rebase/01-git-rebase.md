# Scenario: Simple Rebase without Conflicts

You are working on a feature branch (`feature-y`). Meanwhile, some non-conflicting updates have been made to the `main` branch. You want to rebase your feature branch onto the updated `main` branch to incorporate the latest changes.

#### Initial Setup:

- The `main` branch has a file `example.py` with the following content:
  ```python
  # example.py
  def main():
      print("Hello from main")
  ```

#### Branch `feature-y`:

- In `feature-y`, you add a new function to `example.py`:
  ```python
  # example.py
  def main():
      print("Hello from main")

  def new_feature_y():
      print("Hello from feature Y")
  ```

#### Meanwhile, on `main`:

- Another developer adds a new utility function to `example.py`:
  ```python
  # example.py
  def main():
      print("Hello from main")

  def utility_function():
      print("This is a utility function")
  ```

### Your Challenge:

1. **Rebase `feature-y` onto `main`**.
2. **Ensure that the final `example.py` file includes both the utility function from `main` and the new feature from `feature-y`**.

### Detailed Steps:

#### Step 1: Rebase `feature-y` onto `main`

1. **Fetch the latest changes from the remote repository**:
   ```sh
   git fetch origin
   ```

2. **Checkout your feature branch**:
   ```sh
   git checkout feature-y
   ```

3. **Rebase your feature branch onto `main`**:
   ```sh
   git rebase origin/main
   ```

Since there are no conflicting changes, Git will reapply the commits from `feature-y` onto the latest commit from `main` automatically.

#### Final Verification

Ensure the `example.py` file includes both the utility function from `main` and the new feature from `feature-y`:

```python
# example.py
def main():
    print("Hello from main")

def utility_function():
    print("This is a utility function")

def new_feature_y():
    print("Hello from feature Y")
```

### Solution Verification:

To verify that the challenge was solved correctly, the following criteria should be met:
- The `feature-y` branch contains the rebased changes from `main`.
- The final `example.py` file includes both the utility function from `main` and the new feature from `feature-y`.
- The commit history should reflect a clean rebase, showing the integration of changes from `main` into `feature-y`.

### Detailed Commit History Example:

Assume the initial commit history looks like this:

#### `main` branch:
```
commit 1: Initial commit with example.py
commit 2: Add utility_function to example.py
```

#### `feature-y` branch:
```
commit 1: Initial commit with example.py
commit 2: Add new_feature_y to example.py
```

After rebasing `feature-y` onto `main`, the commit history of `feature-y` will be:
```
commit 1: Initial commit with example.py
commit 2: Add utility_function to example.py
commit 3: Add new_feature_y to example.py (rebased)
```

### Conclusion:

This scenario demonstrates how `git rebase` can be used to incorporate the latest changes from the `main` branch into a feature branch when there are no conflicting changes. It ensures that your feature branch stays up to date with the `main` branch, facilitating smoother integration and deployment.
