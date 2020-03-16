Role Name
=========

Joins linux server to MS Windows active directory and manages authentication via kerberos+sssd. Manages
- domain join
- kerberos setttings
- sssd service

Tested on EL7, Ubuntu 18.04

Requirements
------------

Assumes network is fully configured including DNS and FQDN of the server.

Role Variables
--------------

see defaults/main.yml

<pre>
siteDomain             (default: none)  : name of the dns-domain. Used in krb5.conf.
adauth_realm           (default: none)  : name of the ActiveDirectory realm
krb5_allow_weak_crypto (default: false) : allow krb5 weak crypto algorithms
ldap_user_search_base  (default: none)  : ActiveDirectory search base for users
ldap_group_search_base (default: none)  : ActiveDirectory search base for groups
keytab_root_dir        (default: none)  : network directory path to store created krb5-keytab files
</pre>

Dependencies
------------

This role is written to be standalone.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-role-adauth, tags: [ 'auth' ] }

License
-------

Apache License
Version 2.0, January 2004


Author Information
------------------
https://github.com/mhakala
