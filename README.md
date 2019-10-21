Role Name
=========

Install and configure mediawiki in a docker container	

Requirements
------------

An accessible MariaDB instance

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

Mediawiki Configuration Changes
-------------------------------

#####PHP.ini
- Locate php.ini: php --ini
- In /usr/local/etc/php/, there are two files: php.ini-development and php.ini-production
- Copy one (I used prod last) to ./php.ini
- Change:
```
  # diff php.ini php.ini-production
669c669
< post_max_size = 0M
---
> post_max_size = 8M
822c822
< upload_max_filesize = 100M
---
> upload_max_filesize = 2M
```

#####LocalSettings.ini
```
$wgServer = "http://wiki.thedarkarts.za.net";
```

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
