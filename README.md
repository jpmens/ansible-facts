# gathering own "facts" in Ansible

1. Copy `localsetup` to your ansible `library/` directory
2. Invoke `localsetup` as module in playbook

		---
		- hosts: 127.0.0.1
		  connection: local
		  tasks:
		  - name: Gather our facts
		    action: localsetup keytab=/etc/krb5.keytab
		  - name: Demotemplate
		    action: template src=info.in dest=/tmp/info.txt
3. Use variables

## Files

* `info.in`: Template source.
* `info.txt`: Output produced by template
* `/etc/sysinfo`: provisioned file
