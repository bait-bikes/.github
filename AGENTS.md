# Bait Bikes organization-profile guidance

This repository owns organization-wide public community-health defaults and the GitHub organization profile. Keep product code and credentials out of it.

- Follow the canonical guidance in `ORESoftware/my-ai/AGENTS.md`.
- Treat `profile/README.md` as public marketing copy.
- Keep security reports out of public issues; maintain a clear private reporting route.
- Use explicit paths when staging. Never rebase, force-push, reset, clean, or discard unrelated work.
- Validate Markdown links and inspect the public organization profile after publication.

## Repository-local Git worktrees

- Create or use a Git worktree only when the human operator explicitly authorizes it for the current task. Concurrency or a dirty checkout is not permission by itself.
- Put every authorized worktree at `<repository-root>/tmp/worktrees/<name>`; from the repository root, use `./tmp/worktrees/<name>`. Never place worktrees beside repositories or organization directories.
- Keep `tmp`, `temp`, `tmp/worktrees`, and `temp/worktrees` ignored in the repository-root `.gitignore`. Do not commit files from those directories.
- Relocate or remove a worktree only when the operator explicitly requests it. Before removal, preserve and publish intended changes, verify its commit is represented on the target branch, and confirm there are no tracked, untracked, ignored-sensitive, or in-use files that must survive. Remove it with `git worktree remove <path>` without `--force`; never delete a worktree directory with `rm`.
