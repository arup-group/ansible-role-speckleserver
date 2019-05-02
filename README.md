Role Name
=========

This role installs the SpeckleServer, a design and AEC

Requirements
------------

This is primarily designed to run on a Linux host, with a Redis cache and MongoDB NoSQL database.
These can be provided externally (for instance in AWS or other cloud providers) or via other Ansible roles.

Role Variables
--------------

speckleserver\_server\_name: A name for this SpeckleServer instance.

speckleserver\_url: The canonical web URL for this SpeckleServer instance (default: http://localhost/)

speckleserver\_public\_streams: Allow streams to be publicly published (default: true)

speckleserver\_port: Port for SpeckleServer to listen on (default 3000)

speckleserver\_listen\_ip: IP address to bind to (defaults to 127.0.0.1)

speckleserver\_session\_secret: Session cookie secret: (default "changemeplease")

speckleserver\_mongodb\_uri: MongoDB connection string: (default mongodb://localhost:27017/)

speckleserver\_redis\_host: Redis hostname to connect to (default localhost)

speckleserver\_redis\_port: Redis port (default 6379)

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in
regards to parameters that may need to be set for other roles, or variables that
are used from other roles.

Example Playbook
----------------
    - hosts: servers
      roles:
         - { role: ansible-role-speckleserver  }
      vars:
        speckleserver\_server\_name: 'SpeckleServer Development Environment'
        speckleserver\_url: 'http://speckle.example.com'
        speckleserver\_mongodb\_uri: 'mongodb://mongo.example.com:27017/speckle'
        speckleserver\_redis\_host: 'redis.example.com'

License
-------

BSD

Author Information
------------------

Michael Fleming <michael.fleming@arup.com>
