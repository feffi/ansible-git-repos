# ansible-git-repos

Ansible role to manage git repositories.

[![Build Status](https://img.shields.io/travis/feffi/ansible-git-repos.svg)](https://travis-ci.org/feffi/ansible-git-repos) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-git-repos/total.svg)](https://github.com/feffi/ansible-git-repos) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-git-repos.svg?style=social&label=Fork)](https://github.com/feffi/ansible-git-repos) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-git-repos.svg?style=social&label=Star)](https://github.com/feffi/ansible-git-repos) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-git-repos.svg?style=social&label=Watch)](https://github.com/feffi/ansible-git-repos) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-git-repos/blob/master/LICENSE)

## Requirements

- Ansible 2.3

### ansible.cfg

```yaml
hash_behaviour = merge
```

## Install

Just add the role to your ``requirements.yml`` file:

```yaml
- src: https://github.com/feffi/ansible-git-repos.git
  name: feffi.git-repos
```

## Role Variables

All role based variables are listed below, along with default values:

```yaml
git_repos:
  # Containment directory for pulled git repositories
  containment: "{{ ansible_env.HOME + '/workspace' }}"

  # Git repositories to pull
  repositories: []
```

## Dependencies

None.

## Example Playbook

```yaml
    - hosts: all
      vars:
        git_repos:
          containment: "{{ ansible_env.HOME + '/workspace' }}"
          repositories: []
      roles:
        - { role: feffi.git-repos }
```

Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.git-repos,
            git_repos: {
              containment: "{{ ansible_env.HOME + '/workspace' }}",
              repositories: []
            }
          }
```
