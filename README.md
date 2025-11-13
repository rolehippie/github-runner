# github-runner

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/github-runner)
[![General Workflow](https://github.com/rolehippie/github-runner/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/github-runner/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/github-runner/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/github-runner/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/github-runner/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/github-runner/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/github-runner)](https://github.com/rolehippie/github-runner/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.github__runner-blue)](https://galaxy.ansible.com/rolehippie/github-runner)

Ansible role to install and configure a GitHub self-hosted runner.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [github_runner_api](#github_runner_api)
  - [github_runner_arch](#github_runner_arch)
  - [github_runner_args](#github_runner_args)
  - [github_runner_as_root](#github_runner_as_root)
  - [github_runner_dir](#github_runner_dir)
  - [github_runner_download](#github_runner_download)
  - [github_runner_enterprise](#github_runner_enterprise)
  - [github_runner_envvars](#github_runner_envvars)
  - [github_runner_group](#github_runner_group)
  - [github_runner_groups](#github_runner_groups)
  - [github_runner_hide_sensitive_logs](#github_runner_hide_sensitive_logs)
  - [github_runner_labels](#github_runner_labels)
  - [github_runner_name](#github_runner_name)
  - [github_runner_org](#github_runner_org)
  - [github_runner_reinstall](#github_runner_reinstall)
  - [github_runner_repo](#github_runner_repo)
  - [github_runner_state](#github_runner_state)
  - [github_runner_system](#github_runner_system)
  - [github_runner_token](#github_runner_token)
  - [github_runner_url](#github_runner_url)
  - [github_runner_user](#github_runner_user)
  - [github_runner_version](#github_runner_version)
  - [runner_runner_grouping](#runner_runner_grouping)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### github_runner_api

API URL to access GitHub

#### Default value

```YAML
github_runner_api: https://api.github.com
```

### github_runner_arch

Architecture of the system

#### Default value

```YAML
github_runner_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'x64' }}"
```

### github_runner_args

Optional arguments for the runner

#### Default value

```YAML
github_runner_args:
```

### github_runner_as_root

Install service as root

#### Default value

```YAML
github_runner_as_root: false
```

### github_runner_dir

Home and working path

#### Default value

```YAML
github_runner_dir: /home/runner
```

### github_runner_download

URL to download the runner from

#### Default value

```YAML
github_runner_download: https://github.com/actions/runner/releases/download/v{{ 
  github_runner_version }}/actions-runner-{{ github_runner_system }}-{{ 
  github_runner_arch }}-{{ github_runner_version }}.tar.gz
```

### github_runner_enterprise

Enterprise to register the runner

#### Default value

```YAML
github_runner_enterprise:
```

### github_runner_envvars

Additional env variables injected into .env

#### Default value

```YAML
github_runner_envvars:
```

### github_runner_group

Group user for the runner processes

#### Default value

```YAML
github_runner_group: runner
```

### github_runner_groups

Additional groups for the runner

#### Default value

```YAML
github_runner_groups:
  - sudo
  - docker
```

### github_runner_hide_sensitive_logs

Hide potentially sensitive logs

#### Default value

```YAML
github_runner_hide_sensitive_logs: false
```

### github_runner_labels

Labels for the runner

#### Default value

```YAML
github_runner_labels:
  - self-hosted
```

### github_runner_name

Name of the runner

#### Default value

```YAML
github_runner_name: '{{ ansible_hostname }}'
```

### github_runner_org

Organization to register the runner

#### Default value

```YAML
github_runner_org:
```

### github_runner_reinstall

Always reinstall the service

#### Default value

```YAML
github_runner_reinstall: false
```

### github_runner_repo

Repo to register the runner

#### Default value

```YAML
github_runner_repo:
```

### github_runner_state

State of the runner service

#### Default value

```YAML
github_runner_state: started
```

### github_runner_system

Operating system for the runner

#### Default value

```YAML
github_runner_system: "{{ 'osx' if ansible_system == 'Darwin' else 'linux' }}"
```

### github_runner_token

Personal access token for runner registration token retrieval

#### Default value

```YAML
github_runner_token:
```

### github_runner_url

General URL to access GitHub

#### Default value

```YAML
github_runner_url: https://github.com
```

### github_runner_user

User used for the runner processes

#### Default value

```YAML
github_runner_user: runner
```

### github_runner_version

Version fo the runner

#### Default value

```YAML
github_runner_version: 2.329.0
```

### runner_runner_grouping

Optional group name for the runner

#### Default value

```YAML
runner_runner_grouping:
```

## Discovered Tags

**_github-runner_**

## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
