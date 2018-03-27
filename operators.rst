####################
Operators in general
####################

*LI-DL* has yet only binary operators. They are listed in the table below. Priority 1 is the highest.

+------------+------------+-----------+-------------------------+
| Operator   | Arity      | Priority  | Example meaning         |
+============+============+===========+=========================+
| ``:``      | Binary     | 1         | Range creation          |
+------------+------------+-----------+-------------------------+
| ``*``      | Binary     | 2         | Aplhabet intersection   |
+------------+------------+-----------+-------------------------+
| | ``+``    | | Binary   | 3         | | String concatenation  |
| | ``-``    | | Binary   |           | | Aplhabet difference   |
+------------+------------+-----------+-------------------------+
| ``=``      | Binary     | 4         | Variable assignment     |
+------------+------------+-----------+-------------------------+


Parentheses ( ``(`` and ``)`` ) might be used to override the priority table.

Integers, Floats, Alphabets and Strings always represent themselves when it comes to being an operand. Generators, Ranges and Choices can be used as operand as well, as long as they yield the correct data type.

Example: two generators can be contatenated together, because a generator generates a string. Therefore, concatenating two generators is pretty much the same as concatenating two strings.

Beware of a Choice here, as it is the only construction which can yield several data types. Keep in mind that *LI-DL* performs no check here and you might be surprised by the result (or, more probably, by an exception).

