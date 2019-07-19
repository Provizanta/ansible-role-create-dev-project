Ansible role: Empty C++ project
=========

Create an empty C++ project.

CMake files inspired by:
  - https://github.com/ttroy50/cmake-examples
  - https://github.com/sunsided/cmake/blob/master/CMakeLists.txt


Special thanks to: tomas321

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
        - CXX

    tests: []

These variables can be further used to specify mode details:

    project:
      name:             # str, project name
      version:          # str, format: "major.minor.revision"
      description:
        short:          # str, short project description
        long:           # str, long project description
      author:
        name:           # str, author's full name
        email:          # author's e-mail contact
      settings:         # dict, key represents the setting name, value represents the value

    format:       # str, clang format file content

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
