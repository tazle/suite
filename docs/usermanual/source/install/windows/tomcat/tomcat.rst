.. _install.windows.tomcat.tomcat:

Tomcat installation
===================

The Tomcat Application server is used to host the Boundless Suite web applications. Tomcat itself is a Java application, and some care will be required to configure it appropriately for use.

1. Download :guilabel:`32-bit/64-bit Windows Service Installer` from the Apache website:
   
   * http://tomcat.apache.org/download-80.cgi
   
   .. figure:: img/tomcat_download.png
      
      Tomcat Service Download (32-bit)
   
   .. note:: This download will work on both Windows 32-bit and Windows 64-bit machines, we will be installing the 32-bit service to match the 32-bit Java Runtime installed previously.
   
   .. warning: Boundless Suite requires a recent version of Tomcat supporting Servlet 3.
   
2. Run the tomcat installer.

   .. figure:: img/tomcat_install.png
      
      Apache Tomcat Setup

3. Tomcat is an open source project, distributed using the Apache Software License.

   .. figure:: img/tomcat_license.png
      
      Apache license
      
4. Select :guilabel:`Tomcat` from the list of components, this will include :guilabel:`Service Startup` and :guilabel:`Native` components during installation.

   .. figure:: img/tomcat_components.png
   
      Service Startup and Native component installation

5. During Tomcat configuration supply a :guilabel:`User Name` and :guilabel:`Password` used for Tomcat administrator login.

   .. figure:: img/tomcat_config.png
   
      User Name and Password configuration
   
   .. note:: The Tomcat administrator role ``manager-gui`` is required to interact wit the :guilabel:`Tomcat Manager` used to deploy and monitor Boundless Suite web applications.

6. Browse, if required, to the location of the Java 8 Java Runtime Environment installed previously.

   .. figure:: img/tomcat_jre.png
   
      Java Runtime Environment
      
7. Accept the default Tomcat install location and click :guilabel:`Install` to proceed.

   .. figure:: img/tomcat_location.png
   
      Install location

8. When installation is completed click :guilabel:`Finish` to run the application.

   .. figure:: img/tomcat_done.png
   
      Completing Apache Tomcat Setup

9. To confirm the application is working select :menuselection:`Start --> Apache Tomcat --> Tomcat Welcome`.

   .. figure:: img/tomcat_welcome.png
      
      Tomcat welcome

10. After the service has started you can monitor application status using the taskbar.

    .. figure:: img/tomcat_taskbar.png
      
       Monitor Tomcat
      
    .. note:: This application is available in :menuselection:`Start --> Apache Tomcat --> Monitor Tomcat`.

10. Right click on the the task bar and select :menuselection:`Configure` to open :guilabel:`Apache Tomcat Properties`.
    
    .. figure:: img/tomcat_properties.png
       
       Configure Tomcat
    
    .. note:: This application is available in :menuselection:`Start --> Apache Tomcat --> Configure Tomcat`.
    
11. Change to the the :guilabel:`Java` tab to configure available memory:
    
    * :guilabel:`Initial memory pool`: 256 MB
    * :guilabel:`Maxium memory pool`: 756 MB
    
    .. figure:: img/tomcat_memory.png
       
       Available memory
       
    .. note:: You may wish to increase the above recommendation when working with raster data, or on a larger machine.

12. Add the following additional :guilabel:`Java Options` to optimize memory management for the larger requests expected when working with geospatial data.

    .. figure:: img/tomcat_optimize.png
       
       Java options
       
13. Press :guilabel:`OK` to save the configuration, and use the taskbar to :guilabel:`Stop service` and :guilabel:`Start service` to restart Tomcat with these new settings.

14. Use :menuselection:`Start --> Apache Tomcat --> Tomcat Manager` to open the manager application.
    
    .. figure:: img/tomcat_login.png
       
       Login to Tomcat Manager

    .. figure:: img/tomcat_manager.png
       
       Tomcat Web Application Manager
    
    .. note:: If you missed providing providing a ``manager-gui`` user earlier you can manually provide one now:
       
       From :menuselection:`Start --> Apache Tomcat --> Tomcat Program Directory`. Open the directory :file:`config` and edit the :file:`tomcat-users.xml` with an additional user::
           
           <user username="admin" password="******" roles="manager-gui" />