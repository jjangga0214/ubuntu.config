# .dotfiles

## :warning: CAUTION

Read [CAUTION.md](CAUTION.md) before any execution here.

## project convention

* Most directories have **README.md**. Please refer them to get detail.
* If one can easily grasp role and effect of a certain script by just looking it, detail description is omitted in README.md. 
* Most scripts and README.md do not care about specific upper level use. To know how a script is used(from 'client-side') in overall, one need to look at decription on higher level modules, which are close to project root.

## clone and placement

I prefer to place dotfile project under `$HOME` with name of **.dotfiles**. I even set `alias dot=cd ~/.dotfiles`, which would be automatically configured.

```bash
sudo apt install git && \
cd $HOME && \
sudo git clone https://github.com/jjangga0214/.dotfiles.ubuntu.git .dotfiles
```

## automatic installation and configuration

Basically, this project is to automatically set preferable environment with ease. [install.sh](install.sh) is for that automation. This handles apt, snap, zsh, oh-my-zsh, node, nvm, go and so on. Also, it clone jjangga0214/note to **$HOME/note**.

```bash
sudo bash install.sh
```

## maunal installation and configuration


### upgrade

```bash
sudo bash upgrade.sh
```

### env

#### zsh and oh-my-zsh

zsh and oh-my-zsh would be installed and configured automatically. However, following config is recommended to do manually.

##### default shell

Config zsh as default shell instead of bash. The change would be applied after rebooting.

```bash
sudo -s
chsh -s $(which zsh)
chsh -s $(which zsh) $(whoami)
```

##### spelling check

Enable spelling check by executing the following on zsh.

```zsh
setopt correct
```

##### keep this project in sync

For understanding mantainence strategy, please read [this](oh-my-zsh/README.md#maintenance-of-zsh-and-oh-my-zsh). [oh-my-zsh.sync.sh](oh-my-zsh.sync.sh) exactly does that.

```bash
sudo zsh oh-my-zsh.sync.sh
```

#### gnome extensions

- Clipboard Indicator [[2]](#2)

#### signing git commit with gpg

If you want gpg signiture on git commit, refer [here](https://gist.github.com/ankurk91/c4f0e23d76ef868b139f3c28bde057fc). Note that it might make some git tools such as gitkraken disable to commit.

### util

- chrome: install it from the official website
- blender: install it from ubuntu software center(ver 2.79) or the official website(ver 2.80 beta).

### dev

- vscode: install it by `.deb` file from the official website. This is because vscode's snap app has _several issues [[1]](#1)_. 
- jetbrains toolbox: install it from the official website.

## license

AGPL-3.0-or-later © 2019 Gil B. Chan <bnbcmindnpass@gmail.com>

## footnote

- <a name="1">[1]</a>: keyboard and font bug. Visit [forum.snapcraft.io](https://forum.snapcraft.io/t/keyboard-input-method-doesnt-work-properly-on-snap-application/9901) for further detail.
- <a name="2">[2]</a>: 
[Clipboard Indicator](https://extensions.gnome.org/extension/779/clipboard-indicator/)