<!-- This should be the location of the title of the repository, normally the short name -->
# yaml-fileserver-smb - Ansible script to setup a SMB fileserver

<!-- Build Status, is a great thing to have at the top of your repository, it shows that you take your CI/CD as first class citizens -->
<!-- [![Build Status](https://travis-ci.org/jjasghar/ibm-cloud-cli.svg?branch=master)](https://travis-ci.org/jjasghar/ibm-cloud-cli) -->

<!-- Not always needed, but a scope helps the user understand in a short sentance like below, why this repo exists -->
## Scope

The purpose of this repository is to provide example code to demonstrate how an SaMBa based fileserver can be deployed on a Linux machine.

<!-- A more detailed Usage or detailed explaination of the repository here -->
## Usage

Execute nas.yml using `ansible-playbook nas.yml` to set up a SMB fileserver. The server is accessible by the user `nasuser` and the SMB folder exported is `/nasfolder`


Key files:

nas.yml: Main SMB fileserver configuration
smb-firewall-setup.yml: Firewall configuration options on the SMB server
inventory: Referred by nas.yml to determine host(s) on which to configure the NFS server

Execution:

`ansible-playbook nas.yml`

Configurations:

ansible.cfg: This should have the correct user and ssh key set up for ansible to configure the server. Optionally, if logging is required, please set up the log_path in this file

inventory: Please provide the correct IP or resolvable fqdn for the server(s) on which the configurations need to be completed

nas.yml: Please update the hosts for the correct host(s) on which configuration actions need to run

Cleaning up:

No clean up is required post running the script(s). However, if the nfs server needs to be removed, then the respective states in the nas.yml and firewall.yml can be set to absent or false. systemctl should be run to disable smbd service

<!-- License and Authors is optional here, but gives you the ability to highlight who is involed in the project -->
## License & Authors

If you would like to see the detailed LICENSE click [here](LICENSE).

- Author: Sayan A Ghosh <sayan.acharya.ghosh@kyndryl.com>
- Maintainer: Sayan A Ghosh <sayan.acharya.ghosh@kyndryl.com>

```text
Copyright:: 2022-2022 Kyndryl, Inc

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
