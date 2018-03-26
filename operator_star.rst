##############
Operator ``*``
##############

.. list-table::
   :widths: 10 10
   :stub-columns: 1

   * - Arity
     - Binary
   * - Priority
     - Lower than ``:``, higher than anything else (2)


Allowed operands
----------------

.. list-table::
   :widths: 25 25 70
   :header-rows: 1
   :stub-columns: 2
   
   * - Left operand
     - Right operand
     - Result
   * - Alphabet
     - String
     - Alphabet containing the right operand if it is present in the left operand, empty Alphabet otherwise.
   * - 
     - Integer
     - Alphabet containing the right operand if it is present in the left operand, empty Alphabet otherwise.
   * - 
     - Float
     - Alphabet containing the right operand if it is present in the left operand, empty Alphabet otherwise.
   * - 
     - Alphabet
     - Alphabet containing elements which are present in both operands.
   * - String
     - Alphabet
     - Alphabet containing the left operand if it is present in the right operand, empty Alphabet otherwise.
   * - Integer
     - Alphabet
     - Alphabet containing the left operand if it is present in the right operand, empty Alphabet otherwise.
   * - Float
     - Alphabet
     - Alphabet containing the left operand if it is present in the right operand, empty Alphabet otherwise.


Examples
--------
The resulting alphabets contain always one element, ``Linux``::

    {"Linux"} * "Linux"
    {"Linux"} * {"Linux"}
    {"Linux", "OSX"} * {"Linux", "Windows"}

