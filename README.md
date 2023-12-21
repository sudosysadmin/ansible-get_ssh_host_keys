This Ansible playbook will scrape the SSH host keys from the target devices and store them in two files...
1. /etc/ansible/files/primary_known_hosts
2. ~/.ssh/known_hosts

No credentials are required to grab this information from the target hosts.

The only file that you will need is an inventory file, similar to the `hosts_example` file provided.

Then you will be able to run the playbook using the following `ansible-playbook` command...
```bash
ansible-playbook -i hosts_example get_ssh_host_keys.yaml -e "hostlist=<groupName>"
```
***NOTE***
If the `-e "hostlist=<groupName>"` is not provided, it will be run against all target devices listed in the inventory file.
Also, please note that if any of your variable files are encrypted by `ansible-vault`, the commmand `--ask-vault-pass` switch will need to be added to the above command.
