https://support.typora.io/Draw-Diagrams-With-Markdown/

## GIT - Dev to Uat
#### Run only the first time (before running prereq)
```s
git clone https://github.com/abc/repo-uat.git
cd repo-uat
git remote add upstream https://github.com/abc/repo-dev.git
git config merge.ours.driver true
git checkout main
git checkout upstream/main -- .gitattributes
git commit -m "Added .gitattributes"
git push
```
#### Run each time
```s
git checkout main
git pull --prune
git branch -D release/uat
git fetch upstream
git diff main upstream/main -- ':!/.github/address_spaces.txt' ':!/.github/workflows/context.json'
git checkout -b release/uat
git merge upstream/main --allow-unrelated-histories --strategy-option theirs
git push --set-upstream origin release/uat
```
#### Run pipeline on release/uat branch - only plan
#### Create a pull request into main
#### Run pipeline on main branch
```mermaid
gitGraph
       branch main-qua
       branch main-dev
       branch feature/A
       commit
       checkout main-dev
       commit
       merge feature/A
       checkout main-qua
       commit
       merge main-dev
       checkout main
       commit
       merge main-qua
```