## Git SSH

Follow [this](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) doc 

## Steps for Mac

```
# These could also be in an install script.

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
brew bundle --file ~/.dotfiles/Brewfile

# ...or move to the directory first.
cd ~/.dotfiles && brew bundle
```

## Steps for Winows

### Create symlinks in the Home directory to the real files in the repo.
```
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/.dotfiles/.zshrc ~/.zshrc
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```

### npm
1) Download node js from https://nodejs.org/en/download/

### Oh-my-zsh
1) Download the latest zsh package:
https://packages.msys2.org/package/zsh?repo=msys&variant=x86_64

Example:
```
zsh-5.7.1-1-x86_64.pkg.tar.xz
```

Update:

The package now is compacted using `zstd`, so now we need some "special" extractor.  
So, in my case, I've downloaded this file  
https://repo.msys2.org/msys/x86_64/zsh-5.8-5-x86_64.pkg.tar.zst
And extracted it using the Peazip.  
https://peazip.github.io/zst-compressed-file-format.html

2) Extract the content to your git bash installation dir:

Usually `C:\Program Files\Git`

3) Test it and config zsh:

Open git bash and type:
```
zsh
```

So, this step is important, it seems `zsh` will ask a few configurations, like the tab completion, history, etc.  
Please read the options and set that according to your use.

4) Installing oh-my-zsh, execute the following cmd on git bash

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

5) Configuring zsh as default shell

Edit the `~/.bashrc` file. (create it if it doesn't exist)

Add the following lines at the end of the file

```
# Launch Zsh
if [ -t 1 ]; then
exec zsh
fi
```