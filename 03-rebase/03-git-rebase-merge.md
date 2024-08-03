# Scenario: Concurrent Development with Rebase and Merge

You have a repository with three branches: `main`, `feature-c`, and `feature-d`. Both `feature-c` and `feature-d` branches have diverged from `main` and have their own unique changes. Additionally, both branches have modified the same file, leading to conflicts. 

#### Initial Setup:
- The `main` branch has a file `config.py` with the following content:
  ```python
  # config.py
  settings = {
      "feature": "none"
  }
  ```

#### Branch `feature-c`:
- In `feature-c`, you modify `config.py` to:
  ```python
  # config.py
  settings = {
      "feature": "C"
  }
  ```

#### Branch `feature-d`:
- In `feature-d`, you modify `config.py` to:
  ```python
  # config.py
  settings = {
      "feature": "D"
  }
  ```

### Your Challenge:

1. **Rebase `feature-c` onto `main`**.
2. **Merge `feature-c` into `main`**.
3. **Rebase `feature-d` onto `main`**.
4. **Merge `feature-d` into `main`**.
5. **Resolve any conflicts that arise**.
6. **Ensure that the final `config.py` file in `main` includes both features correctly**.

### Detailed Steps:

#### Step 1: Rebase `feature-c` onto `main`

```sh
# Checkout feature-c branch
git checkout feature-c

# Rebase feature-c onto main
git rebase main
```

#### Step 2: Merge `feature-c` into `main`

```sh
# Checkout main branch
git checkout main

# Merge feature-c into main
git merge feature-c
```

#### Step 3: Rebase `feature-d` onto `main`

```sh
# Checkout feature-d branch
git checkout feature-d

# Rebase feature-d onto main
git rebase main
```

During this rebase, you will encounter a conflict because `feature-c` and `feature-d` have both modified the same line in `config.py`.

#### Step 4: Resolve the Conflict During Rebase

Git will notify you of the conflict and mark the conflicting section in `config.py` like this:

```python
# config.py
settings = {
<<<<<<< HEAD
    "feature": "C"
=======
    "feature": "D"
>>>>>>> main
```

Edit `config.py` to include both features. For example:

```python
# config.py
settings = {
    "feature": "C and D"
}
```

After resolving the conflict, add the resolved file and continue the rebase:

```sh
# Add the resolved file
git add config.py

# Continue the rebase process
git rebase --continue
```

#### Step 5: Merge `feature-d` into `main`

```sh
# Checkout main branch
git checkout main

# Merge feature-d into main
git merge feature-d
```

Since we resolved the conflicts during the rebase, this merge should be straightforward.

#### Final Verification

Ensure the `config.py` file in `main` has the combined functionality:

```python
# config.py
settings = {
    "feature": "C and D"
}
```

### Solution Verification:

To verify that the challenge was solved correctly, the following criteria should be met:
- The `main` branch contains the merged changes from both `feature-c` and `feature-d`.
- Conflicts were resolved correctly and the final `config.py` file includes both features.
- The repository history should reflect the rebases and merges, showing a clean integration of the features.

### Conclusion:

This challenge involves using both rebasing and merging to handle concurrent development and conflicts. Successfully solving it demonstrates advanced proficiency in managing complex Git workflows, including conflict resolution and history rewriting.
