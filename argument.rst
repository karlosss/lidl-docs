########
Argument
########

An object that serves for generating positional parameters (arguments) which are passed to the submitted script.

If a *LI-DL* code contains more ``Argument`` objects, they will be ordered from top to bottom. See the examples.

Since positional parameters are often very similar, it is possible to pass one generator and tell how many positional parameters are to be generated. *LI-DL* then generates them for you.

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
   * - ``count``
     - Integer
     - No
     - An integer ``1``.
     - Must be defined before ``value``.
     - The count of the arguments to be generated. The ``value`` property is evaluated repeatedly.
   * - ``value``
     - String, Integer, Float
     - Yes
     - 
     - Must be defined after ``count``. Must not contain a NULL byte (``\x00``).
     - The description of the form of the argument.

Allowed objects
---------------

None.

Examples
--------

This puts into positional parameters from one to three integers (at random) and a path to a file (in this order)::

    Argument {
        count = 1:3
        value = 0:100
    }

    File {
        name = [5, LOWER_ASCII]
        abspath = "x"
    }

    Argument {
        value = x
    }

