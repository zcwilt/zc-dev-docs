##########################
Table View Controllers
##########################

`TableViewControllers` allow for the rapid development of admin pages that are mainly concerned with doing CRUD
(Create, Read, Update, Delete) actions on a database table.

Currently creating a page of this type involves a lot of copy/pasting/customising an existing page.

TableViewControllers allow for easier building of this type of admin page/view.
They also allow for much easier integion/overriding by plugins.


Page Skeleton
=============

Pages that want to use the table view have a simple skeleton.

.. code-block:: php

    require('includes/application_top.php');

    require_once DIR_FS_CATALOG . DIR_WS_CLASSES . 'QueryBuilder.php';
    require_once DIR_FS_CATALOG . DIR_WS_ADMIN_CLASSES . 'TableViewControllers/TableViewController.php';
    require_once DIR_FS_CATALOG . DIR_WS_ADMIN_CLASSES . 'TableViewControllers/BaseController.php';


    $tableDefinition = [];

    $tableController = (new YourTableController(
        $db, $messageStack, new QueryBuilder($db), $tableDefinition, ))->processRequest();


    ?>
    <!doctype html>
    <html <?php echo HTML_PARAMS; ?>>
    <head>
        <meta charset="<?php echo CHARSET; ?>">
        <title><?php echo TITLE; ?></title>
        <link rel="stylesheet" type="text/css" href="includes/stylesheet.css">
        <link rel="stylesheet" type="text/css" href="includes/cssjsmenuhover.css" media="all" id="hoverJS">
        <script src="includes/menu.js"></script>
        <script src="includes/general.js"></script>
        <script>
            function init() {
                cssjsmenu('navbar');
                if (document.getElementById) {
                    var kill = document.getElementById('hoverJS');
                    kill.disabled = true;
                }
            }
        </script>
    </head>
    <body onload="init()">
    <!-- header //-->
    <?php require(DIR_WS_INCLUDES . 'header.php'); ?>
    <!-- header_eof //-->

    <!-- body //-->

    <?php require "includes/templates/table_view.php"; ?>

    <!-- body_eof //-->

    <!-- footer //-->
    <?php require(DIR_WS_INCLUDES . 'footer.php'); ?>
    <!-- footer_eof //-->
    </body>
    </html>
    <?php require(DIR_WS_INCLUDES . 'application_bottom.php'); ?>


Table Controller Classes
========================


Table Definition Array
======================

The table definition array sets certain parameters that control the building of the table view.

e.g.

.. code-block:: php

    $tableDefinition = ['colKey'           => 'unique_key',
                     'actions'          => [['action' => 'new', 'text' => 'new', 'getParams' => [], 'showOnlyOnEmptyAction' => true]],
                     'defaultRowAction' => '',
                     'columns'          => ['unique_key' => ['title' => TABLE_HEADING_KEY],
                                            'name'       => ['title' => TABLE_HEADING_NAME],
                                            'status'     => ['title' => TABLE_HEADING_STATUS]]


- colKey
  Sets the get parameter for the colums that is the key for links
- actions
  Alows the setting of an array of `Action Buttons` for the table
- defaultRowAction
  Sets the default row action for the table
- columns
  Defines the columns that will be displayed in the table


colKey
======

The `colKey` parameter defines a get parameter ($_GET) name that is used as the index for each row in the table.

For example in the `countries table` this would be `countries_id` and so the entry would be :-

.. code-block:: php

   'colKey' => 'countries_id'


actions
============

Defines one or more action buttons that will be displayed below the table.
For example you may want a `new` button to add a new entry.

Each action entry consists of a number of parameters.


action
-------

This represents the `action` that clicking he button will perform.
e.g setting `action` to `new` will add `action=new` to the button link.

text
------

This is the text that will be applied to the button.


getParams
------------

Additional get parameters that are added to the button link.
Note:
$_GET['page'] will automatically be set if it is already set in the URI.
additionaly the `colKey` parameter will also be automaticaly set in the button URL as well.

showOnlyOnEmptyAction
------------------------

The button will only be shown if there is not an action get parameter.
e.g. $_GET['action'] is not set


defaultRowAction
========================

Normally when the currently selected row of the table is clicked, this will generate an edit action for that row
resource.
This parameter allows for altering that behavior.

.. code-block:: php

   'defaultRowAction' => ''



columns
============

Defines the columns that will be displayed for the table.
