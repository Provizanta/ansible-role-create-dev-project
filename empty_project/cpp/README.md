Ansible role: Empty C++ project
=========

Create an empty C++ project.

Requirements
------------

None

Role Variables
--------------

These variables are defined in the defaults/main.yml:

    path: '.'       # path where the project root should reside

    project:
      license: "MIT"
      languages:
        - C
        - CXX

    platforms: []


These variables can be further used to specify mode details:

    project:
      name:             # str, project name
      description:      # str, project description
      author:
        name:           # str, author's full name
        email:          # author's e-mail contact
      license:          # enum, license, under which the project is licensed

    scm:                # enum, git|mercurial, source control mechanism

Dependencies
------------

None

Example Playbook
----------------

    - hosts: localhost
      roles:
         - role: empty_project/cpp
           vars:
             path: "~/proj/system/"
             project:
               name: "Fantasy project name"
               owner: "Fantasy Corp."
               license: "BSD-3"
             scm: "git"

License
-------

MIT

Author Information
------------------

Tibor Csóka
