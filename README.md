A container for mysql55 on centos6
==================================

Create a data volume to make your write persistent
   $> docker run --name=dbdata -v /var/lib/mysql centos true

Note: you should never delete this container otherwise your data will be gone.

Initialize a new DB:

    $> docker run --rm=true -e MYSQL_ROOT_PASSWORD=welcome0 --volumes-from=dbdata enalean/centos6-mysql55

Run the DB:

   $> docker run -d --volumes-from=dbdata enalean/centos6-mysql55

FAQ
===

Why the hell a new container for mysql?
---------------------------------------

Because we want an environment that match as much as possible what we will
deploy at client side (a RHEL6 and a mysql55 from SCL).

Credits
=======

Strongly inspired from https://github.com/docker-library/docker-mysql
