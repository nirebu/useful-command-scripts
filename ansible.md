# Ansible one liners

- Run an arbitrary command on localhost or any other host

  ```bash
  ansible all -i 'localhost,' -m MODULE -a ARGUMENTS
  ```

- Hash a password for use in a playbook or variable via the `user` module

  ```bash
  ansible all -i 'localhost,' -m debug -a "msg={{ 'MyStrongPassword' | password_hash('sha512') }}"
  ```
