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
