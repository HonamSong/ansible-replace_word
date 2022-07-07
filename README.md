
Role Name
=========

Replace word in file

Supports the following Operating Systems:
-  CentOS 7/8
-  RedHat 7/8
-  RockyOS 8 
-  Ubuntu 18.04
-  Ubuntu 20.04
-  Ubuntu 22.04

Requirements
------------

None.

Role Variables
--------------

|Variable| Type| Required | Default | Comment |
|---|---|---|---|---|
|type         | str | no  | oneline | last keyword line change to 'oneline' or All loine keyword change to 'multiline'|
|filename     | str | yes | NULL    | /path/to/file_name                  |
|regexp_word  | str | yes | NULL    | find keyword                        |
|replace_word | str | yes | NULL    | replace_word                        |
|is_sudo      | str | no  | yes     | choice [yes|no], yes is become yes  |
|is_backup    | bool| no  | True    | choice [true|false]                 |
|is_debug     | bool| no  | False   | choice [true|false]                 |


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: replace_word, type: "oneline", filename: "/root/test", regexp_word: '^test_conf.*d$', replace_word: "test_after abcd", is_backup: false}
or

    - hosts: servers
      roles:
          - role: replace_word
            type: "oneline"
            filename: "/root/test"
            regexp_word: '^test_conf.*d$'
            replace_word: "test_after abcd"
            is_backup: false



License
-------

MIT/BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
