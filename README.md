# ansible-ec2-800-53-remediate
Role to remediate an EC2 instance according to openscap.

Example Playbook:

```
- name: Run openscap scans
  hosts: all
  become: true
  gather_facts: true
  vars:
    scap_reports_dir: "/opt/ansible/scap_reports"
    scan_only: "false"
  roles:
  - role: CivicActions.ec2-800-53-remediate
```


## Important

This role will modify and reboot the host. To only scan and skip the remediation, set the `scan_only` variable to true.
