https://support.typora.io/Draw-Diagrams-With-Markdown/

# GIT
## Dev to Uat
### Run only the first time (before running prereq)
```
git clone https://github.com/abc/repo-uat.git
cd repo-uat
git remote add upstream https://github.com/abc/repo-dev.git
git config merge.ours.driver true
git checkout main
git checkout upstream/main -- .gitattributes
git commit -m "Added .gitattributes"
git push
```
### Run each time
git checkout main
 
git pull --prune
#### Remove
git branch -D release/qua
 
git fetch upstream
 
git diff main upstream/main -- ':!/.github/address_spaces.txt' ':!/.github/workflows/context.json'
 
git checkout -b release/qua
 
git merge upstream/main --allow-unrelated-histories --strategy-option theirs
 
git push --set-upstream origin release/qua
 
#### Run pipeline on release/uat branch - only plan
 
### Create a pull request into main
 
#### Run pipeline on main branch