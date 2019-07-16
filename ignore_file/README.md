Ansible role: ignorefiles
=========

Create an ignore file for a specific source control tool.

Requirements
------------

None

Role Variables
--------------

These variables are defined in default/main.yml

    scm: git

These variables must be specified by the user:

    path:               # path to the project directory
    language:           # project programming language
    ignore: []          # list, lines to be added to the ignorefile

Dependencies
------------

None

Example Playbook
----------------

At least project path and language should be supplied.

    - hosts: localhost
      roles:
         - role: dev/create/ignore_file
           vars:
             path: "~/proj/system/"
             language: "Python"
             ignore:
               - "bin/"

License
-------

MIT

Author Information
------------------

Tibor Csóka
