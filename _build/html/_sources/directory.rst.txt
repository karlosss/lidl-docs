#########
Directory
#########

An object that serves for creation of directories. Automatically takes care of generating a unique set of names for the files contained in the directory. If this is not possible, an error happens.

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
     - The name of the directory.
   * - ``perms``
     - String, Integer
     - No
     - Depends on ``umask``.
     - Must contain exactly three octal numbers/characters.
     - The permissions of the directory.
   * - ``abspath``
     - String
     - No
     - 
     - Must be defined after ``name``.
     - The name of the variable to store the absolute path to the directory to. The path is stored as a string and might be used later.
   * - ``related_name``
     - String
     - No
     - 
     - 
     - Identifies this object with the given name. Useful for links.

Allowed objects
---------------

``File``, ``Directory``, ``Hardlink``, ``Symlink``, ``Fifo``, ``Student`` and ``Startdir``.

Examples
--------

This generates a directory named ``dir`` and three empty regular files inside it. Note that there is a possibility that two or three files will happen to have exactly the same names, in which case *LI-DL* tries to generate those over again, until it finds a set of unique names::

    Directory {
        name = "dir"
        File {
            name = [1, LOWER_ASCII]
        }
        File {
            name = [1, LOWER_ASCII]
        }
        File {
            name = [1, LOWER_ASCII]
        }
    }

