# use-podman

## Installation

```bash
# Checkout in your Claude skills directory
cd ~/.claude/skills
git clone https://github.com/jarrettmeyer/use-podman.git
```

Or, symlink from another checkout location.

```bash
# Checkout in another directory
cd /path/to/git/checkouts/
git clone https://github.com/jarrettmeyer/use-podman.git

# Create a symlink from the checkout directory to Claude skills directory
cd ~/.claude/skills/
ln -s /path/to/git/checkouts/use-podman/ .
```

### Updating

After the initial installation, update this skill by pull changes.

```bash
cd ~/.claude/skills/use-podman
git pull origin main
```

## Rationale

Some users or organizations may prefer `podman` over `docker` due to licensing differences.

## References

- [Claude Skills Documentation](https://code.claude.com/docs/en/skills)
- [Claude Skills (GitHub examples)](https://github.com/anthropics/skills)