Simple playbooks to patch and update clamav definitions

I included a sample ansible.cfg

There is an inventory file with vars embedded into it. The vars can also be made on a group or host level, up to you.

One playbook will patch and is set to run yum/dnf update but as a systemd service. Regardless of whether you sudo -i , su -, or use dzdo. This allows for a standard way or running the patch. This helped in preventing mass audit logs due to the way that elevation was implemented. 

The antivirus playbook copies source definitions and drops them in the approrpiate dir depending on rhel version.

site.yml calls both patch.yml and antivirus.yml.
