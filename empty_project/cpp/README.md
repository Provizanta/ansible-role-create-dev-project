Ansible role: Empty C++ project
=========

Create an empty C++ project.

CMake files inspired by:
  - https://github.com/ttroy50/cmake-examples
  - https://github.com/sunsided/cmake/blob/master/CMakeLists.txt
  - [docs using Sphinx and Doxygen](https://devblogs.microsoft.com/cppblog/clear-functional-c-documentation-with-sphinx-breathe-doxygen-cmake/)

Special thanks to: [tomas321](https://github.com/tomas321)

Requirements
------------

None

Role Variables
--------------

These variables are defined in the defaults/main.yml:

    path: '.'       # path where the project root should reside

    tests: []       # list of test frameworks, catch2|googletest

These variables can be further used to specify mode details:

    project:
      name:             # str, project name
      version:          # str, format: "major.minor.revision"
      description:
        short:          # str, short project description
        long:           # str, long project description
      authors:
        - name:         # str, author's full name
          email:        # str, author's e-mail contact

    build:
      settings:         # dict, key represents the setting name, value represents the value
      format:           # str, clang format file content
      languages:        # list of languages to compile, C|CXX|CUDA|FORTRAN


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
              authors:
                - "Fantasy Corp."
                - name: Mark Jones
                  email: mark@jones.com
              license: "BSD-3"

License
-------

MIT

Author Information
------------------

Tibor Csóka
