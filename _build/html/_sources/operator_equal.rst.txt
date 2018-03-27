##############
Operator ``=``
##############

.. list-table::
   :widths: 10 10
   :stub-columns: 1

   * - Arity
     - Binary
   * - Priority
     - Lowest (4)


Allowed operands
----------------

.. list-table::
   :widths: 25 25 70
   :header-rows: 1
   :stub-columns: 2
   
   * - Left operand
     - Right operand
     - Result
   * - Variable
     - String
     - Right operand is stored in the variable specified by left operand and right operand is returned.
   * - 
     - Integer
     - Right operand is stored in the variable specified by left operand and right operand is returned.
   * - 
     - Float
     - Right operand is stored in the variable specified by left operand and right operand is returned.
   * - 
     - Alphabet
     - Right operand is stored in the variable specified by left operand (deep copy) and right operand is returned.
   * - 
     - Integer range
     - An item is acquired from the right operand, assigned to the ariable specified by left operand, and then returned.
   * - 
     - Float range
     - An item is acquired from the right operand, assigned to the ariable specified by left operand, and then returned.
   * - 
     - Generator
     - An item is acquired from the right operand, assigned to the ariable specified by left operand, and then returned.
   * - 
     - Choice
     - An item is acquired from the right operand, assigned to the ariable specified by left operand, and then returned.
   * - 
     - Variable
     - The value stored in the right operand is copied to the left operand and then returned.

Examples
--------
Variables ``a`` and ``b`` contain the same integer in range from 5 to 10::

    a = 5:10
    b = a

Variable ``int`` contains the integer ``42``::

    int = 42

Variable ``gen`` contains several times ``na`` followed by ``Batman!``. So does the variable ``joker``::

    gen = [5:10, "na"] + " Batman!"
    joker = gen


