# Ansible Role: `<your role>`

> remove this part start

This repository provides a template for ansible roles. create a new repository based on it, named as per <naming scheme>, build and publish your role in there and include it in any ansible repository by specifying the following in `repo-root/requirements.yml`

## versioning
This repository includes a [release-please](https://github.com/googleapis/release-please-action) configuration that versions an ansible role repository as per internal versioning conventions (documentation will follow).
Since this repository is also versioned using this configuration, please make the following changes after creating a new repository based on this template to ensure versioning works properly:
1. remove `./CHANGELOG.md`
2. change the version in `./.release-please-manifest.json` to `0.0.0`

> remove this part end

To include this role in your ansible repository, add the following to  `./requirements.yml` in your repository:

```yaml
- name: <role-name>
  src: git+ssh://git@github.com/< user/org >/iac.ansible-role.<role-name>.git
  version: <version>
```

# Description

explain what your role does short and concise

## Dependencies

###### Ansible Roles
+ list any roles your role depends on here, including those specified in ./meta/main.yml

###### python packages
+ list any python packages your role depends on here, including those specified in .requirements.txt

###### custom ansible modules
+ list any required costum modules that are not included in ./library here

## Requirements

+ list any other requirements here

## Usage

explain in detail how and when your role should or should not be used and describe all functions and common use cases.

For complex structured variables, a codeblock outlining the schema and a separate table with variable descriptions should be added:

schema for example_var:

```yaml
example_var:
  - a_value:
    a_list:
      -
    a_list_of_dicts:
      - a_value:
        another_value:
```


## Role Variables

specify all variables this role accepts here.
Sub-sections and table columns that are not required may be ommitted.

#### feature switches
Variable | Type | Required | Default | Description/purpose
--- | --- | --- | --- | ---


#### group vars
Variable | Type | Required | Default | Description/purpose
--- | --- | --- | --- | ---


#### Host vars
Variable | Type | Required | Default | Description/purpose
--- | --- | --- | --- | ---

## Example Playbook

provide an example of how to implement this role in a playbook. provide multiple examples if use cases differ largely

```yaml
- name: execute my role
  hosts: <group of hosts>
  gather_facts: true
  roles:
    - role: my_role
```