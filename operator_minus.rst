##############
Operator ``-``
##############

.. list-table::
   :widths: 10 10
   :stub-columns: 1

   * - Arity
     - Binary
   * - Priority
     - Higher than ``=``, lower than anything else (3)


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
     - Alphabet containing elements from the left operand, excluding the element from the right operand (if present, left unchanged otherwise).
   * - 
     - Integer
     - Alphabet containing elements from the left operand, excluding the element from the right operand (if present, left unchanged otherwise).
   * - 
     - Float
     - Alphabet containing elements from the left operand, excluding the element from the right operand (if present, left unchanged otherwise).
   * - 
     - Alphabet
     - Alphabet containing elements from the left operand, excluding the elements from the right operand (those who are present, the remaining are untouched).


Examples
--------
The resulting alphabets contain always one element, ``Linux``::

    {"Linux", "Windows"} - {"Windows"}
    {"Linux"} - {3.11, "Windows"}
    {"Linux", "OSX"} - "OSX"

