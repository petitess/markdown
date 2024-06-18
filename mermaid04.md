```mermaid

gitGraph
       branch main-qua
       branch main-dev
       branch feature/A
       commit tag:"v1.0.0"
       checkout main-dev
       commit
```

       <!-- commit
       checkout main-qua
       commit
       merge main-dev
       checkout main
       commit
       merge main-qua -->

```mermaid
%%{init: { 'logLevel': 'debug', 'theme': 'base', 'gitGraph': {'showBranches': true, 'showCommitLabel':true,'mainBranchName': 'main-dev'}} }%%
      gitGraph
        commit id:"NewYork"
        commit id:"Dallas"
        branch MetroLine2
        commit id:"LosAngeles"
        commit id:"Chicago"
        commit id:"Houston"
        branch MetroLine3
        commit id:"Phoenix"
        commit type: HIGHLIGHT id:"Denver"
        commit id:"Boston"
        checkout main-dev
        commit id:"Atlanta"
        merge MetroLine3
        commit id:"Miami"
        commit id:"Washington"
        merge MetroLine2 tag:"MY JUNCTION"
        commit id:"Boston"
        commit id:"Detroit"
        commit type:REVERSE id:"SanFrancisco"
```


```mermaid
gitGraph
       commit
       commit
       branch develop
       checkout develop
       commit
       checkout main
       merge develop
       commit
```

```mermaid
gitGraph
       commit
       branch feature/A
       commit
       checkout main
       merge feature/A
       checkout main
       branch release/qua
       commit
       checkout main
       merge release/qua
       checkout main
       branch main-qua
```
gitGraph
       branch main-qua
       branch main-dev
       commit
       checkout main-qua
       commit
       merge main-dev
       checkout main
       commit
       merge main-qua
       branch feature/A
```