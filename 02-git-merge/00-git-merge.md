    2313  git init
    2314  echo "m c1" >> main.py
    2315  git add . && git commit -m "m c1 " .
    2316  echo "m c2" >> main.py && git add . && git commit -m "m c2" .
    2317  echo "m c3" >> main.py && git add . && git commit -m "m c3" .
    2318  git log
    2319  git checkout -b hotfix
    2320  echo "hotfix c4" >> hotfix.py && git add . && git commit -m "hotfix c4" .
    2321  echo "hotfix c5" >> hotfix.py && git add . && git commit -m "hotfix c5" .
    2322  git log
    2323  git checkout main
    2324  echo "m c6" >> main.py && git add . && git commit -m "m c6" .
    2325  git checkout hotfix
    2326  echo "hotfix c7" >> hotfix.py && git add . && git commit -m "hotfix c7" .
    2327  git log
    2328  git log --oneline
    2329  git checkout main
    2330  git merge hotfix
    2331  git log --oneline