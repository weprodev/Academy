# Git Conventions 
This document outlines our Git workflow guidelines. You'll find information on branch creation, commit structures, and effective team collaboration. 
Conventional Commits provide a standardized convention for writing commit messages. The primary aim is to establish a consistent and semantic structure that is easily interpretable by humans and machines.

- The Github account was integrated with [Jira platform](https://www.atlassian.com/software/jira). 
- There are two main branches: **develop** (staging) and **master** (production)
- All of the pull requests must be merged to develop first, then after testing on staging we’ll deploy on production (master branch)
- For each user story or task, you should create a new branch which begins with the ID of the user story or task `[TICKET_ID]-[CLEAR-NAME]`. 
  for example: BC1-37-create-sticky-navbar, BC1-42-jwt-configuration
- We follow the **four-eyes principle**; each pull request should be reviewed by two developers.
- All the commit messages, will begin with task/user story ID. like this "TICKET-ID-TYPE: clear and good commit message", for example: "BC1-07-feat: Add user authentication page"
- For every change, or new features we must have a ticket for it. 

## Atomic Commits
Three features a commit needs to have to be atomic
1. Single, irreducible unit: Every commit pertains to one fix or feature.
2. Everything works: Don't break the build on any commit.
3. Clear and concise: Purpose is clear from commit message and description.

## Commit Types
- feat: A new feature, It might involve adding a significant functionality or capability to the project.
- fix: A bug fix, It helps distinguish bug fixes from other changes in the version history.
- style: Non-functional code changes (e.g., formatting)
- chore: Routine tasks, such as dependency updates. refers to routine tasks and maintenance activities that do not directly affect the source code. These tasks are essential for the upkeep of the project. for example: 
  - "update npm dependencies to latest versions", or 
  - "bump lodash from 4.17.20 to 4.17.21" 
  - "update ESLint configuration to extend Airbnb style guide" 
  - "add pre-commit hook using Husky"
  - "update build script to include source maps"
  - "update Webpack to version 5"
  - "migrate documentation from Jekyll to Hugo"
  - "delete unused images from assets folder"
  - "add environment variables to .env.example"
  - "update project license to MIT"
  - ...
- test: Adding or modifying tests
- docs: Documentation changes, These changes could include updating README files, adding comments, or improving inline documentation.
- refactor: These changes could involve optimizing algorithms, restructuring directories, or improving code readability.
- perf: Performance improvements
- build: Changes affecting the build system or dependencies
- ci: Changes to continuous integration/configuration
- revert: Reverting a previous commit

## Characteristics of a Good Commit
In Git, a commit is referring to the state of your code at one specific point in time. Commits are used for saving progression, stating changes and merging developed pieces with others work.

### Atomic and focused
It has to represent one and only one logical change. Do not mix several independent changes in one commit.

```git
# Good commit
git commit -m "BC1-32-feat: Add user authentication"

# Bad commit
git commit -m "BC1-32-feat: Add user authentication and update UI styles"
```

### Descriptive Commit Message
Clearly explains what the commit does and why the change was made. 
```git
# Good commit message
git commit -m "BC1-07-fix: Fix Correct null pointer exception in user login"

# Bad commit message
git commit -m "BC1-07-fix: Fix bug"
```

### Follow Conventional Commit Guidelines
Use the standard commit guidelines to keep your git history clean, consistent and easy to read. 
```
# Good commit message following conventional guidelines

git commit -m "BC1-356-feat: add JWT-based authentication"
git commit -m "BC1-334-fix: resolve race condition in login flow"

# Bad commit
git commit -m "BC1-356: add JWT-based authentication"
git commit -m "fix: resolve race condition in login flow"
```

### Properly Scoped
Avoid partial changes that might leave the codebase in an inconsistent state.
```git
# Good commit with proper scope
git commit -m "BC2-234-refactor: split auth logic into separate module"

# Bad commit with mixed scope
git commit -m "BC2-234-refactor: refactor and minor fixes"
```

### Clarity, and NOT Vague or Misleading Messages
Commit messages that are vague or misleading do not provide useful information about the changes.
```git
# Good commit message
git commit -m "BC1-234-chore: delete unused images from assets folder"

# Bad commit message
git commit -m "clean some Stuff"
```

### Related to the changes
Combining unrelated changes into a single commit makes it difficult to isolate specific changes, potentially introducing bugs and complicating the review process.

```git
# Good commit 
git commit -m "BC2-32-fix: Fix loading captcha in login page"

# Bad commit
git commit -m "Update readme and fix login issue"
```


<br><br><br>

---
#### References
- [Atomic commits will help you git legit](https://www.pauline-vos.nl/atomic-commits/)
- [Good Commit VS Bad Commit: Best Practices for Git](https://dev.to/sheraz4194/good-commit-vs-bad-commit-best-practices-for-git-1plc)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Demystifying Conventional Commits](https://angelo.dini.dev/blog/conventional-commits/)
- [How To Improve Your Git Commit Messages Using Conventional Commits](https://dev.to/danywalls/how-to-improve-your-git-commit-messages-using-conventional-commits-49f5)
