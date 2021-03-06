#############
Symlink
#############

An object that serves for creation of symbolic link. A symbolic link is a file containing a path, it might be both valid and invalid. *LI-DL* can do both.

For a valid symlink, a file generated by *LI-DL* must be referenced (``target_file`` property), otherwise the symlink is considered invalid (even if it happens to reference an existing file).

*LI-DL* automatically checks for the count of symlink levels and marks the symlink as invalid if the number of levels exceeds 40.

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
     - See constraints
     - 
     - If ``target`` is not defined, then this is required.
     - The ``related_name`` of the file this link should reference.
   * - ``target``
     - String
     - See constraints
     - 
     - If ``target_file`` is not defined, then this is required.
     - The string to be stored in this link.
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

This generates a valid symlink with link name ``link`` referencing the file ``my_file``. The related name is used to link the link with its target::

    File {
        name = "my_file"
        related_name = "rel"
    }

    Symlink {
        name = "link"
        target_file = "rel"
    }

This is an example of an invalid symlink (it will contain 5 lowercase letters in its path)::

    Symlink {
        name = "link"
        target = [5, LOWER_ASCII]
    }

Note that always either ``target`` or ``target_file`` must be defined (precisely one of them). Therefore, these two links are incorrect and will cause an exception to be raised::

    Symlink {
        name = "bad 1"
    }

    Symlink {
        name = "bad 2"
        target = "xxx"
        target_file = "yyy"
    }

