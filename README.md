# Forking Workflow
The workflow tested in this repo is based on the forking workflow as proposed by [Atlassian](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow). 

The details of the workflow will be split into the **Developers** side and the **Management** side. The key difference between Management and Developers is the ability to approve and merge pull requests.

## Devs Side
1. `fork` public, production repo.
2. set upstream pointer of `fork` to production repo.
```
git remote add upstream repo-directory
```
3. `branch` off on their own `fork` of the repo as `feat/bug-branches`.
    - work on the feature/bug on the `feat/bug-branches`.
    - after completing the feature/bug, merge into the `dev`.
    - ensure ci/cd (unit testing) is present when merging into `dev` branch of the `fork` repo.
4. submit a PR from `fork` upstream into `dev` branch of production repo.
5. repeat steps 3-4 for new features and bugs.
    - ** ensure that `git pull` is done from upstream whenever new changes are made to `dev` branch of the production repo)

## Management Side
1. code review of PR.
2. merge PR into `dev` branch of production repo.
3. when `dev` branch is ready to be pushed to `master` branch as a new version, first merge `dev` into `staging/testing`.
4. do qa testing at `staging/testing` branch.
5. merge `staging/testing` into `master`.
6. create new branch with version number matching the current `master`.
