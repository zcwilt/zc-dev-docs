#############
Documentation
#############

This documentation is built using `Sphinx and RestructuredText
<https://http://www.sphinx-doc.org/en/master/>`_

RestructuredText is similar to Markdown, but adds some extra bells and whistles that allow for much easier
building of structured documentation.

In order to properly contribute to the documentation project you will need to install some additional software.


Installing Documentation
========================

The documentation can be installed from github.

i.e.

`git clone https://github.com/zcwilt/zc-dev-docs.git zen-docs`

This will clone the documentation into a directory called `zen-docs`, you can of course change the directory
name the documentation is cloned into.

Installing Sphinx
=================

Please see the `Sphinx Documentation <http://www.sphinx-doc.org/en/master/usage/installation.html>`_ for installing the software on your computer.

Building Documentation
======================

After editing any files you want to add/change , you will need to run Sphinx to rebuild the documentation.

You will first need to change into the directory where the documentation is stored, i.e. the directory used in the
`git clone` command.

From the command line you should then run
`make clean html`

This will build the documentation in the `_build/html` directory, and you can open the index.html file in this directory
to preview the documentation.


Resources
=========

