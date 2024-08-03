# Scenario: Simple Rebase to Integrate Updates

You are working on a feature branch (`feature-x`) while other changes have been made to the `main` branch. You want to rebase your feature branch onto the updated `main` branch to incorporate the latest changes before continuing your work.

#### Initial Setup:

- The `main` branch has a file `example.py` with the following content:
  ```python
  # example.py
  def main():
      print("Hello from main")
  ```

#### Branch `feature-x`:

- In `feature-x`, you modify `example.py` to add a new function:
  ```python
  # example.py
  def main():
      print("Hello from main")

  def new_feature():
      print("Hello from feature X")
  ```

#### Meanwhile, on `main`:

- Another developer modifies `example.py` to improve the main function:
  ```python
  # example.py
  def main():
      print("Hello from the updated main branch")
  ```

### Your Challenge:

1. **Rebase `feature-x` onto `main`**.
2. **Resolve any conflicts that arise**.
3. **Ensure that the final `example.py` file includes both the updated main function and the new feature**.

### Detailed Steps:

#### Step 1: Rebase `feature-x` onto `main`

1. **Fetch the latest changes from the remote repository**:
   ```sh
   git fetch origin
   ```

2. **Checkout your feature branch**:
   ```sh
   git checkout feature-x
   ```

3. **Rebase your feature branch onto `main`**:
   ```sh
   git rebase origin/main
   ```

During this rebase, you will encounter a conflict because both `main` and `feature-x` have modified `example.py`.

#### Step 2: Resolve the Conflict

Git will notify you of the conflict and mark the conflicting section in `example.py` like this:

```python
# example.py
def main():
<<<<<<< HEAD
    print("Hello from the updated main branch")
=======
    print("Hello from main")

def new_feature():
    print("Hello from feature X")
>>>>>>> ca421af (feature x)
```

Edit `example.py` to combine the changes. For example:

```python
# example.py
def main():
    print("Hello from the updated main branch")

def new_feature():
    print("Hello from feature X")
```

After resolving the conflict, add the resolved file and continue the rebase:

```sh
# Add the resolved file
git add example.py

# Continue the rebase process
git rebase --continue
```

#### Final Verification

Ensure the `example.py` file includes both the updated main function and the new feature:

```python
# example.py
def main():
    print("Hello from the updated main branch")

def new_feature():
    print("Hello from feature X")
```

### Solution Verification:

To verify that the challenge was solved correctly, the following criteria should be met:
- The `feature-x` branch contains the rebased changes from `main`.
- Conflicts were resolved correctly and the final `example.py` file includes both the updated main function and the new feature.
- The commit history should reflect a clean rebase, showing the integration of changes from `main` into `feature-x`.

### Conclusion:

This simple rebase scenario demonstrates how to integrate changes from the `main` branch into a feature branch, resolving any conflicts that arise in the process. It ensures that your feature branch is up to date with the latest changes from `main` before continuing development.
