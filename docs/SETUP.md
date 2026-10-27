# Development Environment Setup

This document describes the one-time setup required to contribute to Mokka.

## 1. Git identity

Commits must be attributed to your GitHub account. Configure it globally or per
repository:

```bash
git config --global user.name  "yasmramos"
git config --global user.email "yasmramos95@gmail.com"
```

> GitHub associates commits with an account through the **verified email** in
> the commit metadata, not through the credentials used to push. Keep the email
> above consistent with a verified address in your GitHub settings so commits
> show up correctly.

## 2. Authentication (HTTPS + Personal Access Token)

Use a Personal Access Token (PAT) instead of a password:

1. Create or refresh a token at <https://github.com/settings/tokens> with access
   to `yasmramos/Mokka` (`repo` scope / contents read+write).
2. Store it for the git credential helper:

```bash
git config --global credential.helper store
echo "https://yasmramos:<YOUR_TOKEN>@github.com" > ~/.git-credentials
chmod 600 ~/.git-credentials
```

**Security notes**

- Never paste a token into chat, issues, commits, or files that get committed.
- Revoke any token that may have been exposed: delete it at
  <https://github.com/settings/tokens> and update `~/.git-credentials`.
- Alternatively use SSH keys (`ssh-keygen -t ed25519`) and switch the remote to
  `git@github.com:yasmramos/Mokka.git`.

## 3. Commit hooks (Conventional Commits)

A `commit-msg` hook rejects messages that do not follow the Conventional
Commits specification, and a `pre-push` hook warns on pushes to `main`.

Enable them once per clone:

```bash
git config core.hooksPath .githooks
```

(Already enabled in this workspace; the setting is local, so every new clone
needs the command above.)

## 4. Branch workflow

- `main` — release-ready code only.
- `develop` — integration branch for daily work.
- `feat/<name>` / `fix/<name>` — cut from `develop`, merged back via pull
  request.

All code, comments and documentation are written in English (see
[`CONVENTIONS.md`](../CONVENTIONS.md)).
