<!-- BEGIN_ANSIBLE_DOCS -->
# ansible-gitlab-podman-runner

An Ansible role to setup a Podman 5.x-based Gitlab Runner on Ubuntu 24.04

## Supported Operating Systems

- Ubuntu 24.04

## Role Arguments



#### Options for `gitlab_runner`

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
| `gitlab_instances` | Gitlab instances which this runner should register with | dict | no |  |
| `config` |  | dict of 'config' options | yes |  |
| `pre_pulled_images` | OCI images that should be pre-pulled on system | list of '' | no | [] |
| `version` | Major version of Gitlab Runner to be installed | int | no | 17 |
| `runner_image` | OCI image to be used for individual runner containers | str | no | docker-registry.punkt.de/docker/podman-extended |
| `repository` |  | dict of 'repository' options | yes |  |

#### Options for `gitlab_runner.config`

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
| `concurrent_runners` | Maximum number of runner containers that can run simultaneously | int | no | 20 |

#### Options for `gitlab_runner.repository`

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
| `apt` | Maximum number of runner containers that can run simultaneously | dict of 'apt' options | no | True |

#### Options for `gitlab_runner.repository.apt`

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
| `repository` | APT repository to use for Gitlab Runner | str | no |  |
| `key_url` | URL to the signing key for the APT repository | str | no |  |

## Dependencies
None.

## Installation
Add this role to the requirements.yml of your playbook as follows:
```yaml
roles:
  - name: ansible-gitlab-podman-runner
    src: https://github.com/punktDe/ansible-gitlab-podman-runner
```

Afterwards, install the role by running `ansible-galaxy install -r requirements.yml`

## Example Playbook

```yaml
- hosts: all
  roles:
    - name: gitlab-podman-runner
```

<!-- END_ANSIBLE_DOCS -->
