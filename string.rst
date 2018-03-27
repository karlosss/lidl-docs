######
String
######

A string is a bunch of characters. It can be used for file names, file contents, the content of ``stdin``, positional parameters and many more. It is pretty much the same as strings in programming languages.

There is one predefined string - the path of the directory the generated Bash script is run in. It might be useful in some cases. It is accessible through the variable ``ROOT``.

Syntax
------
::

    "string content"
    'string content'

As you can see, there is no difference between ``"`` and ``'``. Just bear in mind that the string must start and end with the same type of quotation. The other type of quotes in a string is considered as a literal. 

Mutli-line string are not supported.

Escape sequences
----------------

In *LI-DL* strings, several escape sequences can be used. They are listed below:

.. list-table::
   :widths: 10 40
   :header-rows: 1
   
   * - Sequence
     - Meaning
   * - ``\"``
     - A ``"`` literal (works only for double-quoted strings)
   * - ``\'``
     - A ``'`` literal (works only for single-quoted strings)
   * - ``\\``
     - A ``\`` literal
   * - ``\a``
     - A bell (ASCII 7)
   * - ``\b``
     - A backspace (ASCII 8)
   * - ``\f``
     - A form feed (ASCII 12)
   * - ``\n``
     - A newline (ASCII 10)
   * - ``\r``
     - A carriage return (ASCII 13)
   * - ``\t``
     - A horizontal tab (ASCII 9)
   * - ``\xXX``
     - A byte of hex value ``XX`` (example: ``\x40`` is a ``@``)


Examples
--------
Assigning string to a variable::

    var = "some string"
    another_var = 'another string\nover two lines'

