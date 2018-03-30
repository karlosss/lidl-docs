########
Hardlink
########

An object that serves for creation of hardlinks.

Unlike symbolic links, a hardlink must always reference an existing file.

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
   * - ``target_file``
     - String
     - Yes
     - 
     - 
     - The ``related_name`` of the file this link should reference.
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

None.

Examples
--------

This generates a hardlink with link name ``link`` referencing the file ``my_file``. The related name is used to link the link with its target::

    File {
        name = "my_file"
        related_name = "rel"
    }

    Hardlink {
        name = "link"
        target_file = "rel"
    }

