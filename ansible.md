# Ansible one liners

- Run an arbitrary command on localhost or any other host

  ```bash
  ansible all -i 'localhost,' -m MODULE -a ARGUMENTS
  ```

- Hash a password for use in a playbook or variable via the `user` module

  ```bash
  ansible all -i 'localhost,' -m debug -a "msg={{ 'MyStrongPassword' | password_hash('sha512') }}"
  ```

- Gather the setup of a host and use jq to filter all assigned IPv4, replacing the first line with a plain `{`

  ```bash
  ansible all -i 'localhost,' -u root  -m setup | sed '1c {' | jq '.ansible_facts.ansible_all_ipv4_addresses[]'
  ```
