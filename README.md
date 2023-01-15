```bash
sudo apt update && sudo apt update


sudo apt install git gnome-tweaks curl wget build-essential clang nodejs npm ripgrep fzf stow gh xclip podman

# gnome tweak keyboard
gnome-tweaks

# Keyboard > Capslock > Additional Esc

# tmux
sudo apt install tmux
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

# Install plugin manager:
tmux
# C-b + I

# kitty
sudo apt install kitty
sudo update-alternatives --install /usr/bin/x-terminal-emulator x-terminal-emulator `which kitty` 50
sudo update-alternatives --config x-terminal-emulator

# nvim
sudo snap install --edge nvim --classic

# stow cfgs
git clone https://github.com/hrryndrsn/cfg.git ~/cfg
cd cfg
stow nvim
stow kitty
stow tmux

# open nvim and let packer run
nvim

# add vim alias
echo 'alias vim="nvim"' >> ~/.bashrc
source ~/.bashrc


# slack
wget https://downloads.slack-edge.com/releases/linux/4.29.149/prod/x64/slack-desktop-4.29.149-amd64.deb
sudo apt install ./slack-desktop-4.29.149-amd64.deb


# brave
sudo apt install curl
sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg] https://brave-browser-apt-release.s3.brave.com/ stable main"|sudo tee /etc/apt/sources.list.d/brave-browser-release.list
sudo apt update
sudo apt install brave-browser

# rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# choose custom > complete install to get clippy

source "$HOME/.cargo/env"
rustup target add wasm32-unknown-unknown
rustup target add aarch64-unknown-linux-gnu

# cargo lambda
snap install zig --classic --beta
cargo install cargo-lambda

```
