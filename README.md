# Git Training

This repository is used for training purposes about `Gitflow` workflow.

| Branch    | Environment | URL                                            |
| --------- | ----------- | ---------------------------------------------- |
| `develop` | Staging     | https://develop.bootcamp-git-gitflow.pages.dev |
| `main`    | Production  | https://bootcamp-git-gitflow.pages.dev         |

## Gitflow Workflow

1. Start a New Feature: Create a new feature branch from `develop`.
```bash
git checkout -b feat/my-feature
```
2. Work on the Feature: Make changes, commit them to the feature branch.
3. Finish the Feature: Once the feature is complete, merge it back into `develop`.
```bash
git checkout develop
git merge --no-ff feature/my-feature
```
~~4. Start a Release: Create a release branch from `develop`.~~
```bash
git checkout -b release/1.0.0 develop
```
5. Test and Finalize the Release: Perform final testing, bug fixing, and version bumping on the release branch (or `develop` branch).
6. Finish the Release: Merge the release/`develop` branch into both `main` (and `develop`), and tag it with a version number.
```bash
git checkout main
git merge --no-ff release/1.0.0
git tag -a 1.0.0
git checkout develop
git merge --no-ff release/1.0.0
```
7. Start a Hotfix (if necessary): Create a hotfix branch from `main` to address critical issues.
```bash
git checkout -b hotfix/1.0.1 main
```
8. Finish the Hotfix: Merge the hotfix branch into both `main` and `develop`, and tag it with a new version number.
```bash
git checkout main
git merge --no-ff hotfix/1.0.1
git tag -a 1.0.1
git checkout develop
git merge --no-ff hotfix/1.0.1
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.
