#################
Variable (object)
#################

**This is an object Variable. DO NOT MIX WITH *LI-DL* INTERNAL VARIABLES!**

An object that serves for setting a shell variable for the script.

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
     - Must follow rules for naming shell variables.
     - The name of the variable.
   * - ``value``
     - String, Integer, Float
     - Yes
     - 
     - 
     - The value the variable shall be initialized with.

Allowed objects
---------------

None.

Examples
--------

This puts an integer into a shell variable and a path to a file to another shell variable::

    Variable {
        name = "integer"
        value = 0:100
    }

    File {
        name = [5, LOWER_ASCII]
        abspath = "x"
    }

    Variable {
        name = "PATH"
        value = x
    }

