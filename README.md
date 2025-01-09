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
