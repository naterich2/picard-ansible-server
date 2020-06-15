## nrichman.dev Ansible Control

This repository stores almost all of my config for my home server.  Just about every service that I ran (until recently) was in docker and coordinated with ansible.  Recently, I acquired a server and installed proxmox on it, so now I have VMs for a few tasks.  I decided to continue to use this repository for all the config and store it on one machine to be pushed out to the others.  

For example, I will have an nginx or apache web server on each vm to expose under a subdomain for the vm, but I will store the nginx configs in a template for an ansible "web" role.  This allows me to keep a centralized config for every service I run.  Then when I want to start a new service or migrate an old one to a new machine, I can just change the host the role will be running on.

I'm not exactly sure how ansible is _supposed_ to be used, but I've developed a method that works for me, which is to create a role for each service or each service group that I know I'll want on the same machine.  So the roles folder contains these.  Then the playbooks folder contains a playbook for each role to apply it to a certain or a number of hosts.

This is a continual work in progress.

