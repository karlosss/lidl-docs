#####
Stdin
#####

An object that serves for generating content which will be put onto the stdin of the script.

If a *LI-DL* code contains more ``Stdin`` objects, they will be concatenated from top to bottom. See the examples.

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
   * - ``value``
     - String, Integer, Float
     - Yes
     - 
     - 
     - The description of what should be put onto stdin.

Allowed objects
---------------

None.

Examples
--------

This puts onto stdin from one to three integers (at random) and a path to a file (in this order), all separated by a newline::

    Stdin {
        value = [1:3, 0:100] + "\n"
    }

    File {
        name = [5, LOWER_ASCII]
        abspath = "x"
    }

    Stdin {
        value = x + "\n"
    }

