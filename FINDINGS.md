These are my main findings from the testing for the forking workflow.

Firstly, I will list the steps that were taken during the testing.

## Steps Taken
1. created `fork` from `sunroofgod-testing/forking-workflow`.
        - `fork` includes every single branch from "production" repo.
2. changed default branch on `forked` repo to `dev` branch.
3. added upstream pointer on local to production repo.
```
git remote add upstream https://github.com/sunroofgod-testing/forking-workflow.git
```
4. added .txt file to `master` branch of "production" repo.
5. git pulled on local `dev` branch (`forked` repo.)
        - no changes were made.
