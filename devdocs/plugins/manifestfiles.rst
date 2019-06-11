##########################
Manifest Files
##########################

Each plugin will have a master manifest.php in it's main directory version specific
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

