# Setup WSL with Pyenv and ZSH

## Atualização do Sistema

Execute os comandos abaixo para atualizar os pacotes:

```bash
sudo apt update -y
sudo apt upgrade -y
```

## Instalação do Python

Para instalar apenas o Python:

```bash
sudo apt install python3.11-full python3.11-dev -y
```

Ou para instalar o Python 3.10:

```bash
sudo apt install python3.10-full python3.10-dev -y
```

## Instalação de Pacotes Essenciais

```bash
sudo apt install git curl build-essential dkms perl wget -y
sudo apt install gcc make default-libmysqlclient-dev libssl-dev -y
sudo apt install -y zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev llvm \
  libncurses5-dev libncursesw5-dev \
  xz-utils tk-dev libffi-dev liblzma-dev python3-openssl git
```

## Instalação do Pyenv

```bash
curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash
```

Siga as instruções do Pyenv para finalizar a configuração.

## Instalação do VS Code

Baixe e instale o VS Code a partir do link:
[VS Code Download](https://code.visualstudio.com/download)

## Configuração Opcional

### Instalar e Configurar ZSH

```bash
sudo apt install zsh -y
chsh -s /bin/zsh
zsh
```

### Instalar Oh-my-zsh

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Mais informações: [Oh My Zsh](https://ohmyz.sh/)

### Instalar Spaceship Prompt

```bash
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Altere o arquivo `~/.zshrc` e modifique a linha:

```bash
ZSH_THEME="spaceship"
```

### Instalar Zsh Autosuggestions

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### Instalar Zsh Syntax Highlighting

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### Configurar Plugins no ZSH

Edite `~/.zshrc` e modifique a linha dos plugins:

```bash
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

### Instalar Fonte Opcional

```bash
mkdir -p ~/.fonts
git clone https://github.com/pdf/ubuntu-mono-powerline-ttf.git ~/.fonts/ubuntu-mono-powerline-ttf
fc-cache -vf
```

## Finalização

Reinicie o sistema para aplicar todas as mudanças:

```bash
sudo reboot
```
