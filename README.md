# Ansible Playbook for Local Workstation

The playbook [`workstation.yml`](./workstation.yml) is used for managing the software on
my personal workstation. It is intended to work on recent versions of Ubuntu (tested
on 22.04) but would be mostly portable to other Debian-based distributions if you remove
the use of snaps.

**This is a work in progress: it's constantly evolving as I need new software. I started migrating functionality to roles but haven't got very far with that yet.**

## Bootstrap

The [`bootstrap.sh`](./bootstrap.sh) script installs pip then uses pip to install
ansible.

## Applying the playbook

```bash
# Ensure credentials are fresh
sudo -v
# Run the playbook
ansible-playbook workstation.yml
```

Functionality is (kind of) grouped by tags, which you can use to target a particular set of
actions. For example, to install just the AWS tools:

```bash
ansible-playbook -t aws workstation.yml
```

