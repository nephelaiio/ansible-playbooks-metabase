# nephelaiio.playbooks-metabase

[![Build Status](https://travis-ci.org/nephelaiio/ansible-playbooks-metabase.svg?branch=master)](https://travis-ci.org/nephelaiio/ansible-playbooks-metabase)

Ansible playbook to install [https://metabase.com](Metabase)

## Playbook descriptions

The following lists the group targets and descriptions for every playbook

| playbook     | description         | target       |
| ---          | ---                 | ---          |
| metabase.yml | deploy metabase app | metabase_app |
| postgres.yml | deploy metabase db  | metbase_db   |

## Playbook variables

The following parameters are available/required for playbook invocation

### [metabase.yml](local.yml):
| required | variable               | description                 | default                              |
| ---      | ---                    | ---                         | ---                                  |
| no       | metabase_app_tag       | metabase container tag      | v0.33.2                              |
| no       | metabase_app_container | metabase container name     | metabase                             |
| *yes*    | metabase_db_pass       | metabase db access password | no                                   |
| no       | metabase_db_user       | metabase db access username | metabase                             |
| no       | metabase_db_name       | metabase db name            | metabase                             |
| no       | metabase_db_host       | metabase db access host     | "{{ ansible_default_ipv4.address }}" |
| no       | metabase_db_port       | metabase db access port     | 5432                                 |

### [postgres.yml](local.yml):
| required | variable         | description                 | default                              |
| ---      | ---              | ---                         | ---                                  |
| *yes*    | metabase_db_pass | metabase db access password | no                                   |
| no       | metabase_db_user | metabase db access username | metabase                             |
| no       | metabase_db_name | metabase db name            | metabase                             |
| no       | metabase_db_host | metabase db access host     | "{{ ansible_default_ipv4.address }}" |
| no       | metabase_db_port | metabase db access port     | 5432                                 |

## Dependencies

This playbook has the following git submodule dependencies:

* [plugins/mitogen](https://github.com/dw/mitogen)

## Example Invocation

```
git checkout https://galaxy.ansible.com/nephelaiio/ansible-playbooks-metabase metabase
ansible-playbook -i inventory/ metabase/upgrade.yml
```

## License

This project is licensed under the terms of the [MIT License](/LICENSE)