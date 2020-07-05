# Ansible Singularity Role

[![Build Status](https://travis-ci.com/gabriel-milan/ansible-singularity-role.svg?branch=master)](https://travis-ci.com/gabriel-milan/ansible-singularity-role)

This role installs [Singularity](https://singularity.lbl.gov/) on Linux machines.

## Requirements

None.

## Variables

```yml
singularity_version: "2.5.2"
singularity_temp_path: "/tmp/singularity"
singularity_fname: "singularity-{{ singularity_version }}"
singularity_src_path: "{{ singularity_temp_path }}/{{ singularity_fname }}/"
singularity_url: "https://github.com/singularityware/singularity/releases/download/{{ singularity_version }}/{{ singularity_fname }}.tar.gz"
```

You shouldn't worry about most of the variables here. The ones that really matters are:

* `singularity_version` that tells which version of Singularity you want to install
* `singularity_temp_path` that tells where things will happen (temporary files will be deleted at the end)
* `singularity_url` is the default download path, but you could change it if you wanted

## Use on an Ansible playbook

```yml
- hosts: hpc-nodes
  roles:
    - gabriel_milan.singularity
```