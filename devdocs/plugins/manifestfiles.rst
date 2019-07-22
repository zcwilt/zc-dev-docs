##########################
Manifest Files
##########################

Each plugin will have a master manifest.php in it's main directory and version specific
manifest files in each version directory.

The main manifest file looks like :-

.. code-block:: php
    :caption: main plugin manifest.php

    <?php
    return [
        'pluginType' => 'free',
        'pluginAuthor' => 'plugin author',
        'pluginName' => 'Reward Points',
        'pluginDescription' => 'Reward Points Description',
        'managed' => true,
        'zcVersions' => ['v157'],
        'pluginGroups' => []
    ];


while version specific manifests look like

.. code-block:: php
    :caption: plugin version manifest.php

    <?php
    return [

        'pluginAuthor' => 'plugin author',
        'pluginVersion' => 'v1.0.0',
        'zcVersions' => ['v157'],
    ];

pluginType
==========

Currently we allow only two type, either `free` or `core`. All 3rd party plugins should be marked as
`free`

pluginAuthor
============

A human readable string for the plugin author.

pluginName
==========

A human readable string for the name of the plugin.

pluginDescription
=================

A human readable string describing the plugin.

managed
=======

All plugins written to the new v157 spefication should have `managed => true`. Legacy plugins
can add a manifest file where `managed => false` to allow for listings of plugins installed.

zcVersions
==========

An array of the Zen Cart versions the plugin supports.

pluginGroups
============

`not surrently supported` but will eventually support filtering in admin.

@todo
=====

manifest for file hashes to allow for security and auto upgrades etc.





