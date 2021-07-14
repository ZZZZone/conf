## ZZZZone conf

**如果你有自己的配置，执行命令前记得备份你的配置**

```sh

# install HomeBrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# ====================
# ====== tmux ========
# ====================
brew install tmux

# tmux plug manager
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

mv ~/.tmux.conf ~/.tmux.conf.backup
ln -s zong_conf/tmux/tmux.conf ~/.tmux.conf
mv ~/.tmux.conf.local ~/.tmux.conf.backup.local
ln -s zong_conf/tmux/tmux.conf.local ~/.tmux.conf.local

# ====================
# ====== zsh =========
# ====================

# oh-my-zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

mv ~/.zshrc ~/.zshrc.backup
ln -s -v ~/zong_conf/zsh/zshrc ~/.zshrc

# === zsh with powerline10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

# === zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# === autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

# === git-open
git clone https://github.com/paulirish/git-open.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/git-open

# autojump
brew install autojump

# ====================
# ==== neofetch ======
# ====================
# A command-line system information tool
brew install neofetch


# ====================
# ====== neovim ======
# ====================
brew install neovim

ln -s  -v ~/zong_conf/nvim  ~/.config/nvim
ln -s  -v ~/zong_conf/vim/vimrc ~/.vimrc

# neovim plug requried
pip3 install neovim
brew install node

# install vim-plug
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

# PlugInstall & CocInstall
nvim -c 'PlugInstall | CocInstall -sync coc-json coc-html coc-go coc-sql coc-vimlsp coc-explorer coc-thrift-syntax-support coc-translator|q'


# ====== ideavim ======
ln -s -v ~/zong_conf/vim/ideavimrc ~/.ideavimrc

# ====================
# ===== lazygit ======
# ====================
brew install lazygit

# ====================
# ===== ranger =======
# ====================
brew install ranger


# jq is a lightweight and flexible command-line JSON processor.
brew install jq


# ====================
# ======= fzf ========
# ====================
brew install fzf
$(brew --prefix)/opt/fzf/install

# ====================
# ===== golang =======
# ====================

brew install go


# dlv
# a debugger for the Go programming language 
go install github.com/go-delve/delve/cmd/dlv@latest


#******************************  
			cask

# ====================
# ==== alacritty =====
# ====================
brew install alacritty
brew tap homebrew/cask-fonts
brew install --cask font-hack-nerd-font
ln -s  -v ~/zong_conf/alacritty  ~/.config

# ====================
# ==== stretchly =====
# ====================
# 定时休息提醒app

brew install --cask stretchly

# ====================
# ====== stats =======
# ====================
# 系统状态监控app
brew install --cask stats
```

