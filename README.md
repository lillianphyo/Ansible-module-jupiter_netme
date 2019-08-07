# Ansible Module: jupiter_netme

https://www.hughes.com/technologies/broadband-satellite-systems/jupiter-system

## Usage

An Ansible custom module to push commands for JUPITER VSAT Modem device.

#### Arguments

| Name             | Required | Default | Description |
|------------------|----------|---------|-------------|
| commands         | Yes      | list    | The command input to JUPITER VSAT Modem. Accept list of commands.  |
| first_host_ip    | Yes      | string  | IP Address of first host that has well connected with JUPITER VSAT MODEM. |
| first_host_usr   | YES      | string  | Username of first host.  |
| first_host_pass  | YES      | string  | Password of first host.  |
| sec_host_ip      | YES      | string  | IP Address of VSAT MODEM.|
| sec_host_usr     | YES      | string  | Username of VSAT MODEM.  |
| sec_host_usr     | YES      | string  | Password of VSAT MODEM.  |

#### Examples

```yml
# Push in commands
- name: push command to jupiter vsat modem
  jupiter_netme:
    commands: "route -n"
    first_host_ip: "{{ FirstHostIP }}"
    first_host_usr: "{{ FirstHostUsername }}"
    first_host_pass: "{{ FirstHostPassword }}"
    sec_host_ip: "{{ ModemIP }}"
    sec_host_usr: "{{ ModemUsername }}"
    sec_host_pass: "{{ ModemPassword }}"
```

## Integration

> Assuming you are in the root folder of your ansible project.

Specify a module path in your ansible configuration file.

```shell
$ vim ansible.cfg
```
```ini
[defaults]
...
library = ./library
...
```

Create the directory and copy the python module into that directory

```shell
$ mkdir library
$ cp path/to/module library
```

