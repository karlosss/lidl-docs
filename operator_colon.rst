##############
Operator ``:``
##############

.. list-table::
   :widths: 10 10
   :stub-columns: 1

   * - Arity
     - Binary
   * - Priority
     - Highest (1)


Allowed operands
----------------

.. list-table::
   :widths: 25 25 70
   :header-rows: 1
   :stub-columns: 2
   
   * - Left operand
     - Right operand
     - Result
   * - Integer
     - Integer
     - Integer range, left operand is lower bound and right operand is upper bound.
   * - 
     - Float
     - Float range, left operand is lower bound and right operand is upper bound.
   * - Float
     - Integer
     - Float range, left operand is lower bound and right operand is upper bound.
   * - 
     - Float
     - Float range, left operand is lower bound and right operand is upper bound.


Examples
--------
Integer range::

    5:10

Float range::

    5:8.5

