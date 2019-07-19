###############
FileSytem Class
###############

The File System classs provides a number of methods for loading files from directories within Zen Cart
and where necessary load from overrides and installed plugins.

The File System class is a Singleton and can be instantiated with,

    $fileSystem = FileSystem::getInstance();

note also to use this class in your code, you will need to have a `use` statement.

    use Zencar\\FileSytem\\FileSytem;


methods currently provided are :-

 - loadFilesFromDirectory($rootDir, $fileRegx)
 - listFilesFromDirectory($rootDir, $fileRegx)
 - loadFilesFromPluginsDirectory($installedPlugins, $rootDir, $fileRegx)
 - findPluginAdminPage($installedPlugins, $page)

