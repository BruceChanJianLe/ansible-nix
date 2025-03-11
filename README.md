# Ansible Nix

This is an Ansible playbook that assist the installation of Nix on your Linux.

Install dependencies (ansible, git)
```bash
sudo apt install ansible git -y
```

Installing Nix with Ansible!
```bash
ansible-pull -U https://github.com/brucechanjianle/ansible-nix --ask-become-pass
```

## Note

If you used my dotfiles, which can be setup with ansible as well.
Read more about it [here](https://github.com/brucechanjianle/ansible). The ~/.config/nix/nix.conf will be
tracked by dotfiles instead.

## Older Software on Nix

Nix packages are mostly up to date, however, sometimes, you want to install
an older version of the package. For example, Ubuntu 24.04 only supports `hyprland`
version 0.39.1 and at the writing time of this article, nix `hyprland` is on version
0.45.2 which is incompatitble.


Here, there is a website where it stores the hash to the previous version of software
on nix. https://www.nixhub.io/

## Uninstall

**Multi User**:
```bash
# Remove Nix daemon service
sudo systemctl stop nix-daemon.service
sudo systemctl disable nix-daemon.socket nix-daemon.service
sudo systemctl daemon-reload

# Remove files created by Nix:
sudo rm -rf /etc/nix /etc/profile.d/nix.sh /etc/tmpfiles.d/nix-daemon.conf /nix ~root/.nix-channels ~root/.nix-defexpr ~root/.nix-profile

# Remove build users and their groups
for i in $(seq 1 32); do
  sudo userdel nixbld$i
done
sudo groupdel nixbld
```

Other places where you may want to clean up:
- `/etc/bash.bashrc`
- `/etc/bashrc`
- `/etc/profile`
- `/etc/zsh/zshrc`
- `/etc/zshrc`

[official link](https://nix.dev/manual/nix/2.18/installation/uninstall)
