# Ansible Nix

This is an Ansible playbook that assist the installation of Nix on your Linux.

Install dependencies (ansible, git)
```bash
sudo apt install ansible git -y
```

Setting up new laptop
```bash
ansible-pull -U https://github.com/brucechanjianle/ansible-nix --ask-become-pass
```
