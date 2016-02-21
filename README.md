Postgres Vagrantfile
====================

Clone this repository, `cd` into it and run `vagrant up` (once you have [vagrant](http://vagrantup.com) installed). That's it! You now have Postgres set up with these settings:

 - host: localhost
 - port: 5432
 - username: vagrant
 - password: vagrant
 - database: vagrant

Postgres is also set up with PostGIS to save you the effort should you need it, and also to demonstrate how you can modify the Vagrantfile to install your own extensions.
