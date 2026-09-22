# zsh config

`.zshrc` is my zsh config. Secrets live outside it in `~/.zsh_secrets`
(never committed), which `.zshrc` sources at startup.

## Setup

1. Symlink the rc into place:

   ```sh
   ln -sf "$PWD/zsh/.zshrc" ~/.zshrc
   ```

2. Create your secrets file from the template and fill in real values:

   ```sh
   cp zsh/.zsh_secrets.example ~/.zsh_secrets
   $EDITOR ~/.zsh_secrets
   ```

`~/.zsh_secrets` is gitignored and must never be committed. See
`.zsh_secrets.example` for the full list of expected variables.
