ntp
=========

Install and configure ntp on Ubuntu. From bennojoy.ntp

Requirements
------------

None

Role Variables
--------------

The variables that can be passed to this role and a brief description about
them are as follows. See the NTP configuration documentation for details:

	# The driftfile
	ntp_driftfile: /var/lib/ntp/drifta

	# The server to sync time with
	ntp_server: [0.ubuntu.pool.ntp.org, 1.ubuntu.pool.ntp.org]

	ntp_restrict:                                                           
	  - "restrict -4 default kod notrap nomodify nopeer noquery"
	  - "restrict -6 default kod notrap nomodify nopeer noquery"
	  - "restrict 127.0.0.1"

	ntp_crypto: no
	ntp_includefile: no
	ntp_keys: no
	ntp_trustedkey: no
	ntp_requestkey: no
	ntp_controlkey: no
	ntp_statistics: no
	ntp_broadcast: no
	ntp_broadcastclient: no
	ntp_multicastclient: no

Examples
--------

1) Install ntp and set the default settings.

	- hosts: all
	  roles:
	    - role: ntp

2) Install ntp and set some custom servers.

	- hosts: all
	  roles:
	    - role: ntp
	      ntp_server: [2.ubuntu.pool.ntp.org, 1.ubuntu.pool.ntp.org]

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

Apache

Author Information
------------------

Raging Bal
