Habitat Developer Environment
=============================

.. note:: Habitat as a development environment is no longer being updated. You may want to try using a docker based
          environment instead.

Habitat is a `Vagrant  <https://www.vagrantup.com/>`_  based virtual machine, with the ability to custom-provision
the VM automatically based on settings you decide.

This is great for use on a laptop for portable offline use, or for doing development testing without installing special versions of PHP/MySQL/Apache/etc.

With default settings, it will link a current checkout of the zencart github repository to a domain name that you can access directly from your browser, all from within your own computer.

A yaml-based configuration system lets you customize your system by adding new shared directories which may map to new websites, and automatically clone other github repositories/branches into those websites.

See the links to the left for detailed instructions for installation and customization.


Habitat was inspired by `Laravel Homestead <http://github.com/laravel/homestead>`_

You can contribute to this documentation by forking the `zencart/documentation <https://github
.com/zencart/documentation>`_ repository on github and submitting Pull Requests.


.. toctree::
    :maxdepth: 7
    :hidden:

    installation
    development
    customising
    tools
    technical
