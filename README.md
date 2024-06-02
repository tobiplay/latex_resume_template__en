# LaTeX resume template (en)

## Introduction

This is a LaTeX-based resume template, based on the work by GitHub user [jakegut](https://github.com/jakegut/resume), adapted, refactored, and extended by [tobiplay](https://github.com/tobiplay). This template follows the work that has been made available to the public over at Reddit in [r/EngineeringResumes](https://www.reddit.com/r/EngineeringResumes/).

## Requirements

You need a working installation of Docker on your computer to work with this project. We highly recommend using VS Code as your code editor, as it comes with a number of extensions that we're shipping as part of the dev container config that'll streamline the development process dramatically.

## Getting started

After cloning the repo via ```git clone https://github.com/tobiplay/latex_resume_template__en.git```, you should be able to open the repo in VS Code and see a notification that a dev container is available for this project. Click on the notification and select "Reopen in Container" to open the project in the dev container.

## Development guidelines

Please make sure to follow the guidelines below when contributing to this repo.

### Conventional Commits and commit style

Every commit to this repo should follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) style. This is a lightweight convention on top of the commit message format, which provides an easy set of rules for creating an explicit commit history, thereby increasing readability and making it easier to write automated tools on top of it.

We're asking specifically for the following, minimum commit style:

```
<type>(<scope>): <subject>

<optional body>

<optional footer(s)>
```

Furthermore, in short, all commit messages should:

- be written in the imperative: "fix bug" and not "fixed bug" or "fixes bug"
- not capitalize the first letter (i.e., not "Fix bug", but "fix bug")
- not end with a period (i.e., not "Fix bug.", but "fix bug")

The Angular docs have a good overview on which types to use for which changes. Building upon [their docs](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type), here's a list of types we're using in this repo (to be extended as needed):

- **dev**: changes that affect the dev environment or dev tooling (e.g., dev dependencies, dev container config etc.)
- **ci**: changes to the CI pipeline and/or config
- **docs**: changes to the documentation (e.g., README, docstrings etc.)
- **feat**: a new feature, e.g., a new user story
- **fix**: a bug fix
- **refactor**: a code change that neither fixes a bug nor adds a feature (e.g., renaming a variable or extracting a function).
- **perf**: a code change that improves performance
- **test**: adding missing tests or correcting existing tests
- **style**: changes that do not affect the meaning of the code (e.g., formatting, missing semi-colons etc.)
- **chore**: other changes that aren't considered major refactorings or new features (e.g., deleting a file)

For example, a commit message with the type `feat` could look like this:

```
dev(container): add and set up `Dockerfile`
```

We encourage you to use the scope as much as possible.

### Branches and naming conventions

Following [this blog article](https://dev.to/varbsan/a-simplified-convention-for-naming-branches-and-commits-in-git-il4), we adhere to the following naming conventions for branches:

- `feature/<name>`: for new features, incl. refactorings and removals of existing features
- `fix/<name>`: for bug fixes
- `hotfix/<name>`: for hotfixes, i.e., for changes that need to be deployed to production asap, not following the normal release cycle
- `test/<name>`: an optional branch for testing outside of the ticket system, e.g., for testing a new feature or a bug fix

The overall branch naming convention is as follows:

```
git branch <category>/<reference (optional)>/<description-in-kebab-case>
```

The naming scheme is in kebab case, i.e., all lowercase and words separated by dashes. The reference is optional, but if it's used, it should be the ticket number from the ticket system (most likely the GitHub issue number). The description should be as short as possible, but as long as necessary. It should be descriptive enough to understand what the branch is about. Always use the imperative form, e.g., `add`, `fix`, `remove` etc. and separate words with dashes. The forward slash is used to separate the category from the reference and the description, making it easier to read compared to using dashes everywhere.

As an example, here are some valid branch names:

```
git branch feature/123/add-authentication
git branch fix/123/fix-ml-pipeline
git branch hotfix/123/fix-broken-deployment
```

### How to write a good pull request

Based on [this blog article](https://www.pullrequest.com/blog/writing-a-great-pull-request-description/), here is a template for writing a good pull request description.

```
## What?

I've added support for authentication to implement Key Result 2 of OKR1. It includes model, table, controller and test. For more background, see ticket #JIRA-123.

## Why?

These changes complete the user login and account creation experience. See #JIRA-123 for more information.

## How?

This includes a migration, model and controller for user authentication. I'm using Devise to do the heavy lifting. I ran Devise migrations and those are included here.

## Testing?

I've added coverage for testing all new methods. I used Faker for a few random user emails and names.

## Screenshots (optional)

None.

## Anything Else?

Let's consider using a 3rd party authentication provider for this, to offload MFA and other considerations as they arise and as the privacy landscape evolves. AWS Cognito is a good option, so is Firebase. I'm happy to start researching this path. Let's also consider breaking this out into its own service. We can then re-use it or share the accounts with other apps in the future.
```

There's also more info on [how to properly close a PR](https://dev.to/this-is-learning/how-to-close-a-pull-request-merge-commit-vs-squash-vs-rebase-on-github-14pi?comments_sort=latest) and [a great video-guided lesson](https://dev.to/karaluton/a-guide-to-perfecting-pull-requests-2b66).
