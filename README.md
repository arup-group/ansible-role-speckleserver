speckleServer
=============

This role installs SpeckleServer, a design and AEC data communication and collaboration platform.

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

There are no hard requirements as such aside a webserver to proxy the application traffic.

I would strongly suggest running this alongside a webservice role such as Jeff
Geerling's Apache module (geerlingguy.apache) or NGINX Inc's nginx module (nginxinc.nginx)

Let's Encrypt's Certbot is also useful if you need SSL/TLS security on a public-facing instance (again,
consider geerlingguy.certbot from Jeff Geerling)

Testing
-------

A test suite with molecule is in development.

Example Playbook
----------------
    - hosts: servers
      roles:
         - { role: ansible-role-speckleserver  }
      vars:
        speckleserver_server_name: 'SpeckleServer Development Environment'
        speckleserver_url: 'http://speckle.example.com'
        speckleserver_mongodb_uri: 'mongodb://mongo.example.com:27017/speckle'
        speckleserver_redis_host: 'redis.example.com'

License
-------

BSD

Author Information
------------------

Michael Fleming <michael.fleming@arup.com>
