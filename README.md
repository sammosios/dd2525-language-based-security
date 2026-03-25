Troupe Quick Onboarding

## Prerequisite
Docker must be installed and running.

## Setup
Add the following alias to your shell RC file (`.bashrc`, `.zshrc`, etc.):

```sh
alias trp='docker run -it --rm -v $(pwd):/Troupe/code ghcr.io/troupelang/troupe:latest /bin/bash'
```

Reload your shell:

```sh
source ~/.bashrc   # or ~/.zshrc
```

You can now run `trp` from any project directory.

## Devcontainer Note
The devcontainer is not usable due to outdated system libraries incompatible with the VS Code server.

## Workflow
1. Edit `.trp` files locally.
2. Start the container:

```sh
trp
```

3. Inside the container, run your file:

```sh
./local.sh /workspace/path/to/file.trp
```

## Summary
- Edit locally
- Enter container with `trp`
- Execute via `local.sh`