##############
Operator ``+``
##############

.. list-table::
   :widths: 10 10
   :stub-columns: 1

   * - Arity
     - Binary
   * - Priority
     - Higher than ``=``, same as ``-``, lower than anything else (3)


Allowed operands
----------------

.. list-table::
   :widths: 25 25 70
   :header-rows: 1
   :stub-columns: 2
   
   * - Left operand
     - Right operand
     - Result
   * - String
     - String
     - String, the result of concatenation of left and right operands.
   * - 
     - Integer
     - String, the result of concatenation of left and right operands, converting the right operand to a String.
   * - 
     - Float
     - String, the result of concatenation of left and right operands, converting the right operand to a String.
   * - 
     - Alphabet
     - Alphabet containing elements from the right operand and the element from the left operand.
   * - Integer
     - String
     - String, the result of concatenation of left and right operands, converting the left operand to a String.
   * - 
     - Integer
     - String, the result of concatenation of left and right operands, converting both operand to a String. **DOES NOT SUM THE NUMBERS!**
   * - 
     - Float
     - String, the result of concatenation of left and right operands, converting both operand to a String. **DOES NOT SUM THE NUMBERS!**
   * - 
     - Alphabet
     - Alphabet containing elements from the right operand and the element from the left operand.
   * - Float
     - String
     - String, the result of concatenation of left and right operands, converting the left operand to a String.
   * - 
     - Integer
     - String, the result of concatenation of left and right operands, converting both operand to a String. **DOES NOT SUM THE NUMBERS!**
   * - 
     - Float
     - String, the result of concatenation of left and right operands, converting both operand to a String. **DOES NOT SUM THE NUMBERS!**
   * - 
     - Alphabet
     - Alphabet containing elements from the right operand and the element from the left operand.
   * - Alphabet
     - String
     - Alphabet containing elements from the left operand and the element from the right operand.
   * - 
     - Integer
     - Alphabet containing elements from the left operand and the element from the right operand.
   * - 
     - Float
     - Alphabet containing elements from the left operand and the element from the right operand.
   * - 
     - Alphabet
     - Alphabet containing elements from the left operand and elements from the right operand.


Examples
--------
All these expressions return ``11``::

    1 + 1
    1 + "1"
    "1" + "1"
    "" + 11

This expression returns ``11.0``::

    1 + 1.0

These alphabets contain ``a``, ``b`` and ``c``::

    {"a"} + {"b", "c"}
    {"b", "c"} + "a"


