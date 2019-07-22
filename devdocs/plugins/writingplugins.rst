###############
Writing Plugins
###############

As mentioned earlier, the directory structure for plugins somewhat resembles the normal Zen Cart directories.

As such some files in certain directories will autoload automatically, and other s may need to be loaded manually.

See the sections below for an understanding of where to place files and how those files will be loaded.


PSR 4 Autoloading
=================

Autoloading is provided for Plugins. Two primary namespaces are created for installed plugins.

Zencart\\Plugins\\PluginKey\\Admin

Zencart\\Plugins\\PluginKey\\Catalog

where `PluginKey` is the `unique key` for the plugin with the first charachter upper cased.

You can also use your own namespacing convention for your plugins classes. However as we cannot know
which version of your plugin is installed at runtime, a helper function to get the correct directory is
provided.

e.g.

    $path = $pluginManager->getPluginDirectory($pluginName, $installedPlugins);

where `$pluginName` is the `unique key` for your plugin and `$installedPlugins` is a list of installed
plugins. This variable is provided in the global namespace and therefore availbale throughout the
`initSystem`.

$path will point to the root directory of your plugin, deoendant on the version installed.

e.g.

`zc_plugins/rewardPoints/v1.0.1/`;

You can then register the namespce using :-

    $psr4Autoloader->addPrefix('Author\\\\Plugin', $path . 'some_directory_path' );


again `$psr4Autoload` is a global variable availaboe throughout the `initSystem`


Admin Controllers
=================

To allow for the loading of pages/views in admin, we can't use the old URI structure of

`https://mydomain.com/admindir/somepage.php` as there is then no way to tell if the page is a core page or a plugin
page.

To allow plugin pages to be auto-detected and loaded the URI structure for admin has been changed to a
similar structure as catalog pages.

e.g.

`https://mydomain.com/admindir?cmd=somepage`

The zen_href_link function in admin has been updated to reflect this.


InitSystem
==========

The `initSystem` file auto loader and init_includes can be used within plugins and will load automatically.

i.e. files in the plugin `admin/includes/auto_loader` and `admin/includes/init_includes` direcories will
function exactly as they do in a normal Zen Cart install.

No adjustment needs to be made to file paths used in the `initSytem` auto_loader, as this will be handled
by the plugin infrastructure, inluding ignoring loading if the plugin is not installed.


Support Files
=============

Support files include files that existy within the `includes\extra_definitions`
and `includes/functions/extra_functions` directories.
Again all of these files will be automatically included from the releavant plugin directories.


Page Files
==========

Standard page files in either the plugin admin or catalog directory will load automatically as well as
pulling in language files related to thet page/view.

Language Files
==============

@todo


Template Files
==============

@todo


