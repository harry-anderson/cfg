```bash
sudo apt update && sudo apt update

sudo apt update && \
    sudo apt upgrade -y && \
    sudo apt install -y git gnome-tweaks curl wget build-essential clang nodejs npm && \
    sudo apt install -y unzip ripgrep stow gh xclip podman pkg-config golang && \
    sudo apt install -y ccache htop dconf-editor moreutils wireshark feh && \
    sudo apt clean autoclean && \
    sudo apt autoremove --yes

# gnome tweak keyboard
gnome-tweaks

# Keyboard > Capslock > Additional Esc

# git
gh login auth
git config --global user.email "14777088+hrryndrsn@users.noreply.github.com"
git config --global user.name "Harry Anderson"

#fzf
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install

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

# open nvim and let packer run
nvim

# add vim alias
echo 'alias vim="nvim"' >> ~/.bashrc
# enabled bash vi mode
echo 'set -o vi"' >> ~/.bashrc
source ~/.bashrc

# slack
wget https://downloads.slack-edge.com/releases/linux/4.29.149/prod/x64/slack-desktop-4.29.149-amd64.deb
sudo apt install ./slack-desktop-4.29.149-amd64.deb

# discord
wget https://dl-ptb.discordapp.net/apps/linux/0.0.38/discord-ptb-0.0.38.deb
sudo apt install ./discord-ptb-0.0.38.deb

# brave
sudo apt install curl
sudo curl -fsSLo /usr/share/keyrings/brave-browser-archive-keyring.gpg https://brave-browser-apt-release.s3.brave.com/brave-browser-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/brave-browser-archive-keyring.gpg] https://brave-browser-apt-release.s3.brave.com/ stable main" | sudo tee /etc/apt/sources.list.d/brave-browser-release.list
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
cargo install cargo-expand cargo-lambda cargo-watch

# insomnia
echo "deb [trusted=yes arch=amd64] https://download.konghq.com/insomnia-ubuntu/ default all" \
    | sudo tee -a /etc/apt/sources.list.d/insomnia.list
sudo apt-get update
sudo apt-get install insomnia


# docker
sudo apt-get remove docker docker-engine docker.io containerd runc
# prereqs
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

# add gpg key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# setup repository
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

# test docker
sudo docker run hello-world

# add docker non-root
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world

# aws cli
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
rm -rf aws awscliv2.zip

# sam cli

wget https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip
unzip aws-sam-cli-linux-x86_64.zip -d sam-installation
sudo ./sam-installation/install
sam --version
rm -rf aws-sam-cli-linux-x86_64.zip  sam-installation

```


