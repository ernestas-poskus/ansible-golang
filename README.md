ansible-golang
=========

[![Build Status](https://travis-ci.org/ernestas-poskus/ansible-golang.svg?branch=master)](https://travis-ci.org/ernestas-poskus/ansible-golang)
[![BSD License](http://img.shields.io/badge/license-BSD-blue.svg)](http://opensource.org/licenses/BSD-3-Clause)

Ansible role for managing Golang installtion from golang.org.

Installation
------------

ansible-galaxy install ernestas-poskus.golang

Requirements
------------

None.

Role Variables
--------------

```yaml
---
# defaults file for ansible-golang
golang_role_release: '0.0.1'

# Golang version to install
golang_version: '1.6.2'

# Golang platform
golang_platform: 'linux-amd64'

# Golang name with installed version
golang_name: 'go{{golang_version}}'

# Golang install directory
golang_install_directory: '/opt/{{golang_name}}'

# Golang soft link
golang_link_to: '/opt/go'

# Golang root for GOROOT env variable
golang_root: '{{golang_install_directory}}/go'

# Golang path for GOPATHenv variable
golang_path: '/usr/local/golang_packages'

# Golang owner
golang_owner: 'golang'

# Golang group
golang_group: 'golang'

# Golang directory mode, others than owner and group cannot access Golang
golang_mode: 0750

# Golang compiled binaries path for GOBIN env variable
golang_packages_bin: "{{golang_path}}/bin"

# Golang packages (GOPATH env variable) directory mode, others than owner and group cannot access Golang
golang_packages_directory_mode: 0770
```

Dependencies
------------

None, for role to install.

Example Playbook
----------------

```yaml
- name: Installing Golang
  hosts: all
  sudo: yes
  roles:
    - role: ernestas-poskus.golang
```

License
-------

Copyright (c) 2016, Ernestas Poskus
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this
  list of conditions and the following disclaimer.

* Redistributions in binary form must reproduce the above copyright notice,
  this list of conditions and the following disclaimer in the documentation
  and/or other materials provided with the distribution.

* Neither the name of ansible-golang nor the names of its
  contributors may be used to endorse or promote products derived from
  this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

Author Information
------------------

Twitter: @ernestas_poskus
