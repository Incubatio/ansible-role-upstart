====================
Upstart Ansible Role
====================

:ABOUT: add an upstart service

Vars
====

Mandatory vars::

  {
    upstart_script:
      - <command>
      - huptime --exec python -m SimpleHTTPServer
      - ...

    upstart_name: <service_name>
  }

Optional vars::

  {
    upstart_description: "<description>"

    upstart_start_on:
      - <start_on>
      - "runlevel [2345]"

    upstart_stop_on:
      - <stop_on>
      - "runlevel [!2345]"

    upstart_config:
      - <full_config_line>
      - respawn limit 5 60

    env_vars:
      <key>: <value>

    upstart_pre_start_script: []   # similar to upstart_script
    upstart_post_start_script: []  # similar to upstart_script
    upstart_pre_stop_script: []    # similar to upstart_script
    upstart_post_stop_script: []   # similar to upstart_script
  }
