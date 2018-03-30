####
Fifo
####

An object that serves for creation of fifos (named pipes).

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
     - String, Integer, Float
     - Yes
     - 
     - Must be defined before ``abspath``. Must contain only unix-valid filename characters.
     - The name of the fifo.
   * - ``perms``
     - String, Integer
     - No
     - Depends on ``umask``.
     - Must contain exactly three octal numbers/characters.
     - The permissions of the fifo.
   * - ``abspath``
     - String
     - No
     - 
     - Must be defined after ``name``.
     - The name of the variable to store the absolute path to the fifo to. The path is stored as a string and might be used later.
   * - ``related_name``
     - String
     - No
     - 
     - 
     - Identifies this object with the given name. Useful for links.

Allowed objects
---------------

None.

Examples
--------

This generates a fifo of a random name::

    Fifo {
        name = [5, LOWER_ASCII]
    }

