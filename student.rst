#######
Student
#######

An object that serves for marking the location of the submitted script in the file tree.

This object must exist precisely once in each *LI-DL* code.

There is no need to worry about the permissions - whatever the permissions of the parental directories are, *LI-DL* changes them so that the script can be reached and executed.

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
     - No
     - A string ``Student``.
     - Must be defined before ``abspath``. Must contain only unix-valid filename characters.
     - The name of the file.
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

This way, the student script will be located in the ``etc`` directory::

    Directory {
        name = "etc"
        Student {}
    }

Probably the most common case is to have the student script in the root::

    File {
        name = "a"
    }
    Student {}

