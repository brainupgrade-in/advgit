# Scenario: Simple Rebase without Conflicts

You are working on a feature branch (`feature-y`). Meanwhile, some non-conflicting updates have been made to the `main` branch. You want to rebase your feature branch onto the updated `main` branch to incorporate the latest changes.

#### Initial Setup:

- The `main` branch has a file `main.py` with the following content:
  ```python
  # main.py
  def main():
      print("Hello from main")
  ```

#### Branch `feature-y`:

- In `feature-y`, you add the following code to `featurey.py`:
  ```python
  # featurey.py
  
  def new_feature_y():
      print("Hello from feature Y")
  ```

#### Meanwhile, on `main`:

- Another developer adds a new utility function to `main.py`:
  ```python
  # main.py
  def main():
      print("Hello from main")

  def utility_function():
      print("This is a utility function")
  ```

### Your Challenge:

1. **Rebase `feature-y` onto `main`**.
2. **Ensure that the final includes both files with their latest content**.

### Detailed Steps:

#### Step 1: Rebase `feature-y` onto `main`

1. **Checkout your feature branch**:
   ```sh
   git checkout feature-y
   ```

2. **Rebase your feature branch onto `main`**:
   ```sh
   git rebase main
   ```

Since there are no conflicting changes, Git will reapply the commits from `feature-y` onto the latest commit from `main` automatically.

#### Final Verification

Ensure the `main.py` file includes both commits on `main` and the new feature in `featurey.py`:

```python
# main.py
def main():
    print("Hello from main")

def utility_function():
    print("This is a utility function")

# featurey.py

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
commit 1: Initial commit with main.py
commit 2: Add utility_function to main.py
```

#### `feature-y` branch:
```
commit 1: Initial commit with featurey.py
```

After rebasing `feature-y` onto `main`, the commit history of `feature-y` will be:
```
commit 1: Initial commit with main.py
commit 2: Add utility_function to main.py
commit 3: Add new_feature_y to featurey.py (rebased)
```

### Conclusion:

This scenario demonstrates how `git rebase` can be used to incorporate the latest changes from the `main` branch into a feature branch when there are no conflicting changes. It ensures that your feature branch stays up to date with the `main` branch, facilitating smoother integration and deployment.
