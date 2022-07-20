

Ansible Role Name - replace_text
=========

Replace Text in file

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

Main variable : replace_info ( type is dict )


### dict in variables

|Variable| Type| Required | Default | Comment |
|---|---|---|---|---|
|type         | str | no  | oneline | last keyword line change to 'oneline' or All loine keyword change to 'multiline'|
|is_sudo      | str | no  | yes     | choice yes or no, yes is become true |
|filename     | str | yes | NULL    | /path/to/file_name                   |
|regexp_word  | str | yes | NULL    | find keyword                         |
|replace_word | str | yes | NULL    | replace_word                         |
|is_backup    | bool| no  | true    | choice true or false                 |
|is_debug     | bool| no  | alse   | choice true or false                 |


Dependencies
------------

None.

Example Playbook
----------------
Here are some examples of how to use the role.

#### The "oneline" type changes the <u>**"last line"**</u> of matching text.
#### The "multiline" type changes the **<u><span style="color:orange">"ALL line"</span></u>** of matching text.


    - hosts: servers
      roles:
         - role: replace_text
           replace_info:
             - { "type": "oneline", "filename": "/root/sshd_config", "regexp_word": '^test_conf.*d$', "replace_word": "test_after abcd", "is_backup": false}
             - { "type": "multiline", "filename": "/root/sshd_config2", "regexp_word": '^test_conf.*d$', "replace_word": "test_after abcd", "is_backup": true}

or

    - hosts: servers
      roles:
          - role: replace_word
            replace_info:
              - type: "oneline"
                filename: "/root/test"
                regexp_word: '^test_conf.*d$'
                replace_word: "test_after abcd"
                is_backup: false
              - type: "multiline"
                filename: "/root/test"
                regexp_word: '^test_conf.*d$'
                replace_word: "test_after abcd"
                is_backup: false
                is_debug: true
                is_sudo: true
                



License
-------

MIT/BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
