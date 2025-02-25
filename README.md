# Git Commit Standards Handbook

## Description
This handbook provides guidelines for writing clear, consistent, and structured Git commit messages. Standardized commits enhance collaboration, maintainability, and debugging while improving automation for changelogs and release tracking. Follow these best practices to keep a clean and readable project history.

## References
This guide is inspired by best practices compiled from:
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Git Commit Message Guidelines by Toni Bardina](https://gist.github.com/tonibardina/9290fbc7d605b4f86919426e614fe692)
- [Git Commit Message Guidelines by Qoomon](https://gist.github.com/qoomon/5dfcdf8eec66a051ecd85625518cfd13)

## Why Standardized Commits Matter

Clear and structured Git commit messages improve collaboration, 
simplify code reviews, and enhance project maintainability. 
They also streamline debugging and enable better automation for changelogs, release tracking, and CI/CD workflows.

## Commit Message Format

A commit message should follow this structure:

```
<type>(optional scope): <short description>

[optional detailed explanation]

[optional footer with metadata]
```

### 1. Commit Types
Each commit should begin with one of these standardized types:

- **feat**: Introduces a new feature
- **fix**: Fixes a bug
- **docs**: Updates documentation
- **style**: Changes that do not affect code behavior (e.g., formatting)
- **refactor**: Code restructuring without changing behavior
- **perf**: Performance improvements
- **test**: Adds or modifies tests
- **ci**: Updates CI/CD configuration
- **build**: Changes build scripts or dependencies
- **revert**: Reverts a previous commit

Example:
```sh
git commit -m "feat: add user authentication system"
```

### 2. Scope (Optional)
The scope provides context for the change. Use a relevant module or component name.

Common examples:
- **ui**: User interface changes
- **auth**: Authentication module
- **db**: Database-related changes
- **api**: Backend API updates

Example:
```sh
git commit -m "fix(auth): resolve token expiration issue"
```

### 3. Description
The description should:
- Be concise (≤50 characters)
- Use the imperative mood (e.g., "add login API" instead of "added login API")

### 4. Commit Body (Optional)
Provides additional context if needed. Keep lines ~72 characters long.

Example:
```
fix(auth): resolve token expiration issue

Tokens were expiring prematurely due to incorrect time zone handling.
This fix ensures proper UTC calculations to maintain session validity.
```

### 5. Footer (Optional)
The footer includes metadata such as issue references and breaking changes.

- **Breaking changes**: Use `BREAKING CHANGE:` followed by an explanation.
- **Issue references**: Use `Closes #123` or `Fixes #456`.

Example:
```
breaking change: migrate from local auth to OAuth

Closes #101
```

## Best Practices

### 1. Keep Commits Atomic
Each commit should focus on a single logical change to improve traceability.

### 2. Avoid WIP (Work in Progress) Commits
Use feature branches or draft commits instead of pushing incomplete changes.

### 3. Use Present Tense
- ✅ "fix bug in session handler"
- ❌ "fixed bug in session handler"

### 4. Keep History Clean
- Use `rebase` instead of `merge` when possible.
- Squash commits in feature branches before merging to `main`.

### 5. Reference Issues
Link commits to relevant tickets for easier tracking in project management tools.

## Example Commit Messages

```
feat(ui): implement dark mode toggle

Users can now switch between light and dark themes.
```

```
fix(db): optimize index usage for queries

Improves query performance by adding proper indexing.
Fixes #402
```

```
breaking change: deprecate legacy API endpoints

Old endpoints `/v1/users` and `/v1/orders` are removed.
Clients must migrate to `/v2` versions.
```

## Conclusion

By adhering to these guidelines, you can ensure that your Git commit messages are clear, consistent, 
and useful for everyone involved in the project. 
This not only improves the readability of the project history but also enhances collaboration and maintainability. 
Happy committing!