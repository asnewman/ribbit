# ribbit

A simple tool for managing AI agent coding sessions with git worktrees.

## Demo

![ribbit demo](ribbit-demo.gif)

## Installation

Copy the script to your PATH:

```bash
sudo cp ribbit /usr/local/bin/ribbit
```

Or add this directory to your PATH in your shell profile:

```bash
export PATH="$PATH:/path/to/this/directory"
```

## Usage

```bash
# Create new agent worktree with shared files (symlinked)
ribbit implement-user-auth --share .env,.env.local

# Create agent worktree with copied files (independent)
ribbit fix-login-bug --clone .env,.env.local

# Create agent worktree without shared files
ribbit fix-login-bug

# List active agent worktrees
ribbit list

# Clean up current agent worktree (run from agent directory)
ribbit cleanup
```

## What it does

- Creates isolated git worktree: `../repo-branch-name/`
- Creates new branch with your specified name
- Symlinks shared files from main repo
- Drops you in the worktree ready for your AI agent

Each agent gets its own directory and branch, solving the problem of multiple AI agents working in parallel on the same repository.