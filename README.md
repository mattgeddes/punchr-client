punchr-client
=============

A simple Ansible role to deploy and start the [Punchr](https://github.com/dennis-tra/punchr/) client.

Requirements
------------

No additional prerequisites imposed by this Ansible role outside any dictated by the [Punchr](https://github.com/dennis-tra/punchr/) team. This role ought to work on most Unix-like systems and architectures (perhaps with some tweaking), but tested on Debian/Ubuntu with systemd, OpenBSD and FreeBSD on amd64, aarch64 and armv7l.

Role Variables
--------------

* `punchr\_enabled`:
   * Description: Whether to deploy and enable the punchr service or remove it.
   * Default value: `false`
* `punchr\_ver`:
   * Description: Version of punchr client to deploy/enable.
   * Default value: `v0.9.0`
* `punchr\_user`:
   * Description: User to run Punchr client as.
   * Default value: `nobody`
* `punchr\_base`:
   * Description: Directory to install Punchr client under
   * Default value: `/usr/local`
* `punchr\_home`:
   * Description: Writable directory for Punchr state
   * Default value: `/var/run/punchr`
* `punchr\_bin`:
   * Description: Format for the filename of the Punchr binary
   * Default value: `punchr\_cli\_{{ ansible\_system | lower }}\_{{ arch\_table[ansible\_architecture]}}`
* `punchr\_uri`:
   * Description: URL to retrieve the Punchr binary from
   * Default value: `https://github.com/dennis-tra/punchr/releases/download/{{ punchr\_ver }}/{{ punchr\_bin }}`

Dependencies
------------

None known.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: mattgeddes.punchr-client }

License
-------

Apache-2.0

Author Information
------------------

mattgeddes on Github.
