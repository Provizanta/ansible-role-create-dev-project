Ansible role: create reate license
=========

Create a license file with a prefiled project information.

Requirements
------------

None

Role Variables
--------------

    license:        # enum, license type
    project:
      name:         # project name
      path:         # project root path
      owner:        # project owner

Dependencies
------------

None

Example Playbook
----------------

All variables are mandatory.

    - hosts: localhost
      roles:
         - role: dev/create/license
           vars:
             license: bsd-3
             project:
               name: "test"
               path: "~/proj/system/"
               owner: "Test Corp."

License
-------

MIT

Author Information
------------------

Tibor Csóka
