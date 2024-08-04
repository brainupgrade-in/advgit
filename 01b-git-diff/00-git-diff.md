2239  git init
 2240  echo "matrix" >> matrix.py
 2241  git add . && git commit -m  "matrix" 
 2242  echo "matrix_reloaded" >> matrix.py 
 2243  git add .
 2244  git diff 
 2245  git diff --staged
 2246  git diff HEAD
 2247  echo "matrix_revolutions" >> matrix.py 
 2248  git status
 2249  git diff
 2250  git diff --staged
 2251  git diff HEAD
