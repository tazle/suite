.. _sysadmin.clustering.install:

Installing the clustering extension
===================================

The clustering extension is not installed by default in :ref:`installations <install>` of Boundless Suite. It must be installed separately and then later :ref:`enabled <sysadmin.clustering.setup>`.

.. note:: Prior to installation of the clustering extension, it is important to ensure that you have set up an external data directory, located in a shared location that all GeoServer instances will be able to access.

Install
-------

Windows
~~~~~~~

The clustering extension is set to be installed on the :guilabel:`Components` page of the :ref:`installer wizard <install.windows>`. Expand the :guilabel:`GeoServer Extensions` by clicking the plus, and then check the box next to :guilabel:`Clustering`.

If Boundless Suite was installed without the clustering extension, first stop the OpenGeo Jetty service, then run the installer again, and at the :guilabel:`Components` page of the installer wizard, uncheck all other components aside from :guilabel:`Clustering`, and then continue with the install.

A restart of the OpenGeo Jetty service will be required.

OS X
~~~~

The clustering extension is not currently supported on using the OS X installer, as Boundless Suite for OS X is not designed to be used in a production environment. If you would like to use Clustering on OS X, use Boundless Suite for Application Servers.

Linux
~~~~~

The clustering extension is available in a collection of two separate packages::

  geoserver-jdbcconfig
  geoserver-cluster

To install the clustering extension, use the package manager.

Red Hat / CentOS::

  yum install geoserver-jdbcconfig
  yum install geoserver-cluster

Ubuntu::

  apt-get install geoserver-jdbcconfig
  apt-get install geoserver-cluster

A restart of GeoServer is not required.

Application Servers
~~~~~~~~~~~~~~~~~~~

For installation when using Boundless Suite for Application Servers, please `contact us <http://boundlessgeo.com/about/contact-us/>`__.

Verification
------------

To verify that the installation of the extension was successful, look for the existence of a ``jdbcconfig`` and ``cluster`` directory inside the GeoServer data directory. If these directories were created and contain files, the installation was successful.
