#############
Plugin System
#############

.. toctree::
    :maxdepth: 7
    :hidden:

    directorystructure
    manifestfiles
    languagefiles
    installerclasses
    sqlinstallation
    writingplugins
    debugingplugins
    pluginmanagerclass


While we had started a plugin architecture for the V2 Develop branch, there was naturally a lot of concern over the fact that current plugins would no longer work and would need extensive rewriting.

Now it is also the case that plugins will also need modification for the v156 and later branches, although in the main this mainly relates to the new template/css for admin along with some other minor tweeks.

Many plugins do not take advantage of a lot of the new notifiers added to v15x which in some cases mean they need to
overrite/amend Zen Cart core files, and for a more automated plugin system this will need to change.

As well, installation of plugins is labour intensive on the part of shop owners/Developers, where files from the
plugins need to be moved to multiple directories within the Zen Cart framework.

Given this it is intended to introduce a new plugin infrastructure into the v157 branch.

However it should be noted that we are not going to force plugin authors to rewrite plugins to conform to this new plugin framework.

Plugins that work with the current code will continue to work.



