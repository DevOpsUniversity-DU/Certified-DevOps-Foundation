`Ad-Hoc commands are one-liner ansible commands that performs one task on the target host.`
`It allows you to execute simpleone-line task against one or group of hosts defined on the inventory file configuration.`

## Ansible Ad-Hoc Commands to use when SSH Keys configured with target hosts

```
how to run ansible ad-hoc commands ( default inventory )

	ansible all -m setup
        ansible qa -m ping
        ansible dev -m shell -a "free -m"
        ansible iat -m copy -a "src=/tmp/naresh.txt dest=/tmp"
        ansible prod -m file -a "path=/tmp/helousername.txt state=touch"

how to run ansible ad-hoc with custom inventory

	ansible all -i /path/to/inventory ping
        ansible dev -i /path/to/inventory -m copy -a "src=/tmp/new.txt dest=/tmp"

how to run ansible ad-hoc with super user (root)

        ansible all -i /path/to/inventory -b ping
        ansible dev -i /path/to/inventory -m copy -a "src=/tmp/new.txt dest=/tmp" -b
```
