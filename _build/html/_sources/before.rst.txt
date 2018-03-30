######
Before
######

An object that serves for providing additional shell commands **before** the submitted script is executed.

*LI-DL* cannot do any validity checks, therefore using this might result in generating an invalid Bash script. Do not use this unless you are absolutely sure what you are doing!

Do not forget that shell commands must be separated by semicolons (``;``) or newlines (``\n``).

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
   * - ``script``
     - String
     - Yes
     - 
     - 
     - Shell commands to be executed.

Allowed objects
---------------

None.

Examples
--------

This sets an alias. If the submitted script uses unescaped ``ls``, instead of directory listing, a scary output will appear::

    Before {
        script = "alias ls='echo Segmentation fault.'\n"
    }

