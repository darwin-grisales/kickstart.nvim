# Workstation Baseline - WSL2 + Neovim + Desarrollo Cloud

> Documento de referencia para reconstruir el entorno de desarrollo principal.

## Componentes principales

- WSL2 + Zsh
- Homebrew
- Mise
- Neovim
- Python, Java, Rust, Go, Terraform
- pnpm + TypeScript LSP
- uv + herramientas Python

## Instalación base

```bash
sudo apt-get install build-essential
sudo apt install xclip xsel
```

## Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

```bash
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv zsh)"' >> ~/.zshrc
source ~/.zshrc
```

## Herramientas Brew

```bash
brew install git unzip ripgrep
brew install neovim
brew install mise
brew install lua luarocks
brew install uv
```

## Mise

```bash
echo 'eval "$(mise activate zsh)"' >> ~/.zshrc
source ~/.zshrc
```

```bash
mise use -g python@latest java@21 rust@latest go@latest terraform@latest
```

## Python

```bash
uv pip install --python $(which python) pynvim
```

```bash
uv tool install black
uv tool install isort
uv tool install yamllint
```

## Node y pnpm

```bash
npm install -g pnpm
pnpm setup
source ~/.zshrc
```

```bash
pnpm add -g neovim
```

## Language Servers

```bash
pnpm add -g typescript typescript-language-server @angular/language-server @angular/language-service yaml-language-server prettier
```

## Rust

```bash
cargo install tree-sitter-cli
```

## Verificación

```bash
python --version
java --version
rustc --version
cargo --version
go version
terraform version
node --version
pnpm --version
nvim --version
```

## Health Check

```bash
nvim --headless "+checkhealth" +qa
```
