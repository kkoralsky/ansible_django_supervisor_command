Django supervisor command
=========

Single Django manage command to run permanently through supervisor.

Requirements
------------

Django app

Role Variables
--------------

- `app` - app name; used for dir structure, supervisor service naming, python path naming etc. (required)
- `django_command` - manage command with all necessary commandline options (required)
- `app_name`  - use to distinguish django dir struct. python path naming
- `program_name` - use for supervisor service name only
- `django_settings_module` - python module path to settings module to use
- `django_settings_tpl` - template for django settings to use
- `supervisor_conf_tpl` - template for supervisor config file

Dependencies
------------

- [django_supervisor](http://github.com/xkoralsky/django_supervisor.git)

Example Playbook
----------------

    - hosts: web-worker
      roles:
         - role: django_supervisor_command
           app: my_app
           django_command: neverending_command --with-options 3

License
-------

BSD
