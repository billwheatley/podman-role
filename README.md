podman-role
=========

Ansible Role to install and configure Podman in rootless mode.

This was mostly created for OpenMandriva as simple `dnf install podman` does not bring in all dependencies or the rootless config like fedora or Debian does.

Requirements
------------

Should work with:

- Red Hat family Distros (ex: Fedora, RHEL, Alma, Rocky)
- Debian family Distros (ex: Debian, Ubuntu, Mint)
- OpenMandriva Distros

Specifically Tested with:

- Fedora 42
- OpenMandriva Rome (circa June 2025)
- Debian 12

Role Variables
--------------

- `users` - (For OpenMandriva) An array of the users you want to be able to run podman rootless.  This will be ignored for other distros and does not produce errors if supplied

Example Playbook
----------------

With users for OpenMandriva (user are ignored on other distros and do not produce errors if supplied)

    - hosts: servers
      roles:
         - role: podman-role
           users:
             - bwheatley
             - jsmith
             - djones

With Red Hat Family and/or Debian Family Distros

    - hosts: servers
      roles:
         - role: podman-role

License
-------

GPLv2

Author Information
------------------

Bill Wheatley
