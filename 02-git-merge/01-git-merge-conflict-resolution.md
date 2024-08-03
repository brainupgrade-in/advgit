# Challenge Scenario: Multiple branches, concurrent development, and resolving conflicts.

You have a repository with three branches: `main`, `feature-a`, and `feature-b`. Both `feature-a` and `feature-b` branches have diverged from `main` and have their own unique changes. Moreover, both branches have modified the same section of a file, which will cause conflicts when merging.

Here are the steps to set up the scenario:

1. **Initial Setup**:
   - `main` branch has a file `app.py` with the following content:
     ```python
     # app.py
     def main():
         print("Hello from main")
     ```

2. **Branch `feature-a`**:
   - In `feature-a`, you modify `app.py` to:
     ```python
     # app.py
     def main():
         print("Hello from feature A")
     ```

3. **Branch `feature-b`**:
   - In `feature-b`, you modify `app.py` to:
     ```python
     # app.py
     def main():
         print("Hello from feature B")
     ```

### Your Challenge:

1. **Merge `feature-a` into `main`**.
2. **Merge `feature-b` into `main`**.
3. **Resolve any conflicts that arise**.
4. **Ensure that the final `app.py` file in `main` includes both features correctly**.

### Detailed Steps:

#### Step 1: Merge `feature-a` into `main`

```sh
# Checkout main branch
git checkout main

# Merge feature-a into main
git merge feature-a
```

#### Step 2: Merge `feature-b` into `main`

```sh
# Merge feature-b into main
git merge feature-b
```

At this point, you will encounter a conflict because both `feature-a` and `feature-b` have modified the same line in `app.py`.

#### Step 3: Resolve the Conflict

Git will notify you of the conflict and mark the conflicting section in `app.py` like this:

```python
# app.py
def main():
<<<<<<< HEAD
    print("Hello from feature A")
=======
    print("Hello from feature B")
>>>>>>> feature-b
```

#### Step 4: Resolve the Conflict

Edit `app.py` to include both features. For example:

```python
# app.py
def main():
    print("Hello from feature A and feature B")
```

After resolving the conflict, add the resolved file and commit the changes:

```sh
# Add the resolved file
git add app.py

# Continue the merge process
git commit
```

#### Final Verification

Ensure the `app.py` file in `main` has the combined functionality:

```python
# app.py
def main():
    print("Hello from feature A and feature B")
```

### Solution Verification:

To verify that the challenge was solved correctly, the following criteria should be met:
- The `main` branch contains the merged changes from both `feature-a` and `feature-b`.
- Conflicts were resolved correctly and the final `app.py` file includes both features.
- The repository history should reflect the merges and conflict resolutions.

### Learnings:

This challenge requires a deep understanding of Git merging, conflict resolution, and proper handling of concurrent development efforts. Successfully solving it demonstrates proficiency in managing complex scenarios in Git.
