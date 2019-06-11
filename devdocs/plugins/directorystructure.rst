##########################
Directory Structure
##########################

Plugins written for the new achitecture will reside in the zc_plugins directory.
Within their directory, the plugins can add directories that mimic the main Zen Cart directories.
note how each plugin also has a versioned directory. This allows for automated upgrades and the possiblity
of downgrading as well.

e.g.

- zc_plugins

  - rewardPoints
  - manifest.php

    - v1.0.0
    - manifest.php

      - admin

        - includes

          - auto_loaders
          - init_includes
          - extra_datafiles
          - classes
          - languages

        - includes

          - functions

            - extra_functions

          - templates
          - etc

    - v1.0.1
    - manifest.php

      - admin

        - includes

          - auto_loaders
          - init_includes
          - extra_datafiles
          - classes
          - languages

        - includes

          - functions

            - extra_functions

          - templates
          - etc
