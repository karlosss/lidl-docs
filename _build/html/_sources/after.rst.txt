#####
After
#####

An object that serves for providing additional shell commands **after** the submitted script is executed.

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

This adds a message to stdout. Might be useful for checking whether the submitted script has an ``exit`` statement in it::

    After {
        script = "echo 'If you do not exit, you will see this.'\n"
    }

