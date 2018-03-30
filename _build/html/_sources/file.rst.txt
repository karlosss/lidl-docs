####
File
####

An object that serves for creation of regular files.

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
     - The name of the file.
   * - ``perms``
     - String, Integer
     - No
     - Depends on ``umask``.
     - Must contain exactly three octal numbers/characters.
     - The permissions of the file.
   * - ``content``
     - String, Integer, Float
     - No
     - Empty file.
     - 
     - The content of the file.
   * - ``abspath``
     - String
     - No
     - 
     - Must be defined after ``name``.
     - The name of the variable to store the absolute path to the file to. The path is stored as a string and might be used later.
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

This generates a file of a random name with its absolute path stored in it. The variable ``x`` is the reason why the compiler cannot have a symbol table - it would be undefined::

    File {
        name = [5, LOWER_ASCII]
        abspath = "x"
        content = x
    }

