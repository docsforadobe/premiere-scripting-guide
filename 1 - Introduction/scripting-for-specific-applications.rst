.. _scripting-for-specific-applications:

Scripting for specific applications
===================================

On startup, all Adobe JavaScript-enabled applications execute JSX files that they find in their startup
directories; some of these are installed by applications, and some can be installed by scripters. The policies
of different applications vary as to the locations, write access, and loading order.
In addition, individual applications may look for application-specific scripts in particular directories, which
may be configurable. Some applications allow access to scripts from menus; all of them allow you to load
and run scripts using the ExtendScript Toolkit.
For details of how to load and run scripts for any individual application, see the JavaScript Scripting Guide
for that application.


.. _startup-scripts:

Startup scripts
---------------
A script in a startup directory might be executed on startup by multiple applications. If you place a script in
such a directory, it must contain code to check whether it is being run by the intended application. You can
do this using the appName static property of the BridgeTalk class. For example::

    if ( BridgeTalk.appName == "bridge" ) {
        //continue executing script
    }

If a script that is run by one application will communicate with another application or add functionality
that depends on another application, it must first check whether that application/version is installed. You
can do this using the ```BridgeTalk.getSpecifier()`` static function. For example::

    if ( BridgeTalk.appName == "bridge-2.0" ) {
        // Check to see that Photoshop is installed.
        if ( BridgeTalk.getSpecifier( "photoshop", 10 ) ){
            // Add the Photoshop automate menu to the Adobe Bridge UI.
        }
    }

For details of interapplication communication, see Chapter 5, :ref:`interapplication-communication-with-scripts`.


.. _javascript-variables:

JavaScript variables
--------------------
Scripting shares a global environment, so any script executed at startup can define variables and functions
that are available to all scripts. In all cases, variables and functions, once defined by running a script that
contains them, persist in subsequent scripts during a given application session. Once the application is
quit, all such globally defined variables and functions are cleared. Scripters should be careful about giving
variables in scripts unique names, so that a script does not inadvertently reassign global variables
intended to persist throughout a session.
