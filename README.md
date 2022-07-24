# youtous/ansible-ufw-smart-rules
[![pipeline status](https://gitlab.com/youtous/ansible-ufw-smart-rules/badges/master/pipeline.svg)](https://gitlab.com/youtous/ansible-ufw-smart-rules/-/commits/master)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
[![GitHub Repo stars](https://img.shields.io/github/stars/youtous/ansible-ufw-smart-rules?label=✨%20youtous%2Fansible-ufw-smart-rules&style=social)](https://github.com/youtous/ansible-ufw-smart-rules/)
[![Gitlab Repo](https://img.shields.io/badge/gitlab.com%2Fyoutous%2Fcaddy--consul--docker?label=✨%20youtous%2Fansible-ufw-smart-rules&style=social&logo=gitlab)](https://gitlab.com/youtous/ansible-ufw-smart-rules/)
[![Licence](https://img.shields.io/github/license/youtous/ansible-ufw-smart-rules)](https://github.com/youtous/ansible-ufw-smart-rules/blob/master/LICENSE)

# THIS ROLE IS STILL IN DEVELOPMENT, DO NOT USE IN PRODUCTION

Manage **ufw** firewall using a single target state and reconcile the existing one.

It works by:
  - scanning the **current state** of the rules for a given desired set of rules, 
  - remove the existing rules not matching the **target state**,
  - add the rules not already present in the **current state**.

This way of managing the firewall using UFW through a **target state** reduces the complexity of the firewall management by implementing a single desired state without dealing with the existing rules.

### Requirements

- ansible-core 2.11+
- [community.general](https://galaxy.ansible.com/community/general) collection
- [jc](https://github.com/kellyjonbrazil/jc) on YOUR system: `pip3 install jc`
- [jmespath](https://github.com/jmespath/jmespath.py) on YOUR system: `pip3 install jmespath`
- [netaddr](https://pypi.org/project/netaddr/) on YOUR system: `pip3 install netaddr`
- Packages that must be present on the target system:
  - ufw

### Usage

Installation from [ansible galaxy](https://galaxy.ansible.com/youtous/ufw_smart_rules): `ansible-galaxy install youtous.ufw_smart_rules`

```yaml
- name: docker prune secrets and configs
  ansible.builtin.include_role:
    name: youtous.ufw_smart_rules
  vars:
```

### License

MIT
