# git-worktree-runner (`git gtr`) cheatsheet

Repo: https://github.com/coderabbitai/git-worktree-runner

## One-time setup (per repo)

```bash
git gtr config set gtr.editor.default cursor
git gtr config set gtr.ai.default claude

# optional: copy env templates into new worktrees
git gtr config add gtr.copy.include "**/.env.example"

# optional: run dependency install after creating worktrees
git gtr config add gtr.hook.postCreate "npm install"
```

## Daily workflow

```bash
# create worktree
git gtr new my-feature

# create + open editor / AI
git gtr new my-feature --editor
git gtr new my-feature --ai
git gtr new my-feature -e -a

# open existing worktree in editor / AI tool
git gtr editor my-feature
git gtr ai my-feature

# run command inside a worktree
git gtr run my-feature npm test

# navigate to a worktree
cd "$(git gtr go my-feature)"

# list and remove
git gtr list
git gtr rm my-feature
```

## Navigation shortcut (`gtr cd`)

```bash
# add to ~/.zshrc or ~/.bashrc
eval "$(git gtr init bash)"

# then
gtr cd my-feature
gtr cd 1   # 1 means main repo
```

## Core commands

```bash
# create
git gtr new <branch> [--from <ref>] [--from-current] [--editor] [--ai]

# open in configured editor
git gtr editor <branch> [--editor <name>]

# start configured AI tool (pass-through args after --)
git gtr ai <branch> [--ai <name>] [-- args...]

# print path for cd
git gtr go <branch>

# run command in worktree
git gtr run <branch> <command...>

# remove worktree(s)
git gtr rm <branch>... [--delete-branch] [--force] [--yes]

# rename worktree + local branch
git gtr mv <old> <new> [--force] [--yes]

# copy files to worktrees
git gtr copy <target>... [--all] [--dry-run] [--from <source>] [-- <pattern>...]

# list worktrees
git gtr list [--porcelain]

# manage config
git gtr config {get|set|add|unset|list} <key> [value] [--global]

# cleanup
git gtr clean [--merged] [--dry-run] [--yes]

# diagnostics / metadata
git gtr doctor
git gtr adapter
git gtr version
```

## Most useful flags

```bash
# new
git gtr new feature-x --from v1.2.3
git gtr new feature-x --from-current
git gtr new feature/x --folder feature-x-short
git gtr new feature-x --name backend --force   # same branch in multiple worktrees

# rm
git gtr rm feature-x --delete-branch --force --yes

# copy
git gtr copy feature-x -- ".env*" "*.json"
git gtr copy -a -n -- "**/.env*"   # preview for all worktrees

# clean merged PR/MR worktrees
git gtr clean --merged --dry-run
git gtr clean --merged --yes
```

## High-value config keys

```ini
# where worktrees live (default: sibling <repo>-worktrees)
gtr.worktrees.dir = ~/worktrees/my-project

# optional folder prefix for new worktrees
gtr.worktrees.prefix = wt-

# default base branch
gtr.defaultBranch = main

# defaults
gtr.editor.default = cursor
gtr.ai.default = claude

# copy patterns (multi-valued)
gtr.copy.include = **/.env.example
gtr.copy.exclude = **/.env.local
gtr.copy.includeDirs = node_modules
gtr.copy.excludeDirs = node_modules/.cache

# hooks (multi-valued)
gtr.hook.postCreate = npm install
gtr.hook.postCreate = npm run build
gtr.hook.postRemove = echo "cleaned"

# UI color: auto|always|never
gtr.ui.color = auto
```

## Notes

- `1` is a special ID for the main repo in commands like `go`, `run`, `ai`, and `cd`.
- `git gtr mv` renames only the local branch; remote branch names are unchanged.
- `git gtr clean --merged` requires `gh` (GitHub) or `glab` (GitLab) installed and authenticated.
- If worktrees are inside the repo (for example `.worktrees`), add that directory to `.gitignore`.
