generate-certificate
=========

This role generates an elasticsearch certificate, handling setting and unsetting ES_PATH_CONF.

Requirements
------------

A multi instance elasticsearch cluster.

Role Variables
--------------

variable name | type | description | default value
------------- | -------- | ------------------------ | -------------
es_generator_instance_name | string | name of the elastic instance that will generate the certificate, not including server name and hyphen | main
override_existing_certificate | boolean | set to true to override existing certificate | false
es_user | string | elasticsearch built in user | elasticsearch

Dependencies
------------

None

Example Playbook and Inventory
----------------
Playbook:

    - name: generate certificate
      hosts: generator
      roles:
        - role: generate-certificate
      vars:
        es_generator_instance_name: main
        override_existing_certificate: true
        
Inventory:

    [generator]
    elasticserver1


License
-------

BSD

Author Information
------------------

Just a frustrated user who didn't want to do this manually.
