# Project Conventions

These rules apply to every repository in this workspace and are enforced by the
assistant for all future work.

## Language

- **All source code identifiers must be written in English** (variables,
  functions, classes, modules).
- **All code comments must be written in English.**
- **All documentation (READMEs, guides, API docs, commit messages, pull request
  descriptions) must be written in English.**

## Git Workflow

- Default integration branch: `main`
- Working / development branch: `develop` — all day-to-day feature work is
  committed on `develop`.
- Never force-push to shared branches without explicit approval.

### Commit Message Format (Conventional Commits)

Commits must always follow the [Conventional Commits](https://www.conventionalcommits.org/)
specification, written in English:

```
<type>(<optional scope>): <description>

[optional body]

[optional footer(s)]
```

Allowed types:

| Type       | Purpose                                                   |
|------------|-----------------------------------------------------------|
| `feat`     | A new feature                                             |
| `fix`      | A bug fix                                                 |
| `docs`     | Documentation only changes                                |
| `style`    | Formatting, missing semicolons, etc. (no logic change)    |
| `refactor` | Code change that neither fixes a bug nor adds a feature   |
| `perf`     | Code that improves performance                            |
| `test`     | Adding or correcting tests                                |
| `build`    | Build system or dependency changes                        |
| `ci`       | CI configuration and scripts                              |
| `chore`    | Maintenance tasks (keep repo tidy, update gitignore, etc.)|
| `revert`   | Reverts a previous commit                                 |

Rules:

1. Description uses the imperative mood ("add", not "added"/"adds").
2. Description starts with a lowercase letter and has no trailing period.
3. Breaking changes use `!` after the type/scope or a `BREAKING CHANGE:` footer.
4. One logical change per commit.

Examples:

```
feat(auth): add JWT token refresh endpoint
fix(ui): prevent duplicate submit on form click
docs(readme): document develop branch workflow
chore(git): configure GitHub credentials and hooks
```

## GitHub Authentication

- Credentials are provided through Git credential helpers using a Personal
  Access Token (PAT). The token is stored in the local credential cache and is
  never committed to any repository.
- User: `yasmramos`
- Email: `yasmramos95@gmail.com`

## Security Note

The access token used during setup was shared in chat. Because it is now
considered exposed, it should be **revoked and regenerated** at
https://github.com/settings/tokens once the initial clone/push is completed.
