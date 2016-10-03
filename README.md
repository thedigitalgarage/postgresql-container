PostgreSQL Docker images
========================

This repository contains Dockerfiles for PostgreSQL images for the Digital Garage.

For more information about using these images with the Digital Garage, please see the
official [Digital Garage Documentation](http://docs.thedigitalgarage.io/using_images/db_images/postgresql.html).

Versions
---------------
PostgreSQL versions currently provided are:
* postgresql-9.2
* postgresql-9.4
* postgresql-9.5


Installation
----------------------
Choose either the CentOS7 or RHEL7 based image:

*  **CentOS7 based image**

    This image is available on DockerHub. To download it run:

    ```
    $ docker pull thedigitalgarage/postgresql-92-centos7
    ```

    To build a PostgreSQL image from scratch run:

    ```
    $ git clone https://github.com/thedigitalgarage/postgresql.git
    $ cd postgresql
    $ make build VERSION=9.2
    ```

**Notice: By omitting the `VERSION` parameter, the build/test action will be performed
on all provided versions of PostgreSQL.**


Usage
---------------------------------

For information about usage of Dockerfile for PostgreSQL 9.2,
see [usage documentation](9.2/README.md).

For information about usage of Dockerfile for PostgreSQL 9.4,
see [usage documentation](9.4/README.md).

For information about usage of Dockerfile for PostgreSQL 9.5,
see [usage documentation](9.5/README.md).

Test
---------------------------------

This repository also provides a test framework, which checks basic functionality
of the PostgreSQL image.

*  **CentOS based image**

    ```
    $ cd postgresql
    $ make test VERSION=9.2
    ```
+By using the `TEST_CASE` parameter you can choose a test case subset to be run against the image, eg:

    $ cd postgresql
    $ make test VERSION=9.2 TEST_CASE="run_general_tests run_replication_test"


**Notice: By omitting the `VERSION` parameter, the build/test action will be performed
on all provided versions of PostgreSQL.**
