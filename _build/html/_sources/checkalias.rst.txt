##########
CheckAlias
##########

An object that serves for checking if the submitted script has a correctly set alias.

*LI-DL* does no checking here. If you enter a malformed name of the alias, the result might behave incorrectly.

Allowed properties
------------------

.. list-table::
   :widths: 10 10 10 10 10 50
   :header-rows: 1
   
   * - Property name
     - Allowed types
     - Required
     - Default value
     - Constraints
     - Description
   * - ``name``
     - String
     - Yes
     - 
     - 
     - The name of the alias to be checked.

Allowed objects
---------------

None.

Examples
--------

This checks wheter the alias ``hello`` is working well::

    CheckAlias {
        name = "hello"
    }

