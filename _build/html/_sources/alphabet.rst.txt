########
Alphabet
########

An alphabet is similar to a set from programming languages - more occurences of a single element are redundant. The aplhabet is used as a set where a generator might take the characters from.

Although alphabets in general usually consist of single characters, alphabets in *LI-DL* can contain whole strings as their "characters", or even integers and floats. This offers more possibilities of usage.

Alphabet elements might be of arbitrary type - besides strings, integers and floats, aplhabets might also contain generators (upon evaluation, a string is generated), ranges (a number is generated) choices (an item is acquired), or even another alphabets (an item is chosen at random). It is usually not a good idea to do this, but sometimes this might come in handy.

Since alphabets are very much like sets, usual set operations may be done with them - like union (operator ``+``), intersection (operator ``*``), or difference (operator ``-``).

Several alphabets are used very often. Therefore, *LI-DL* introduces some predefined alphabets. They are:

.. list-table::
   :widths: 20 50
   :header-rows: 1
   
   * - Variable name
     - Content description
   * - ``LOWER_ASCII``
     - English characters from ``a`` to ``z``.
   * - ``UPPER_ASCII``
     - English characters from ``A`` to ``Z``.
   * - ``DIGITS``
     - String digits from ``0`` to ``9``.
   * - ``WHITESPACE``
     - Horizontal tab (ASCII 9), newline (ASCII 10), and space (ASCII 32).
   * - ``UNPRINTABLE``
     - Unprintable bytes, ASCII from 0 to 31 and ASCII 127.
   * - ``SPECIAL``
     - Printable, nonalphanumeric bytes (examples are ``@`` or ``%``).
   * - ``ONE_BYTE``
     - ASCII one-byte characters, from 0 to 127.
   * - ``ALL_BYTES``
     - Bytes from 0 to 255.
   * - ``LOWER_CZECH``
     - Czech lowercase characters (examples are ``ě`` or ``ů``).
   

Syntax
------

The alphabet is enclosed in curly brackets (``{`` and ``}``) and its elements are separated by commas (``,``).
::

    {"a", "b", "c"}
    {"a", 1, "hello"}
    {"a", [1, LOWER_ASCII], "c"}


Examples
--------
A generator to generate 10-characters long word consisting of ``a``, ``b`` and ``c``::

    [10, {"a", "b", "c"}]

A generator to generate a word consisting of all czech lowercase characters::

    [10, LOWER_ASCII + LOWER_CZECH]

A generator to generate a text of 10 lorem ipsum words (note the trick to get rid of the trailing space at the end of the text)::

    [9, {"lorem ", "ipsum ", "dolor ", "sit ", "amet "}] + 
    [1, {"lorem", "ipsum", "dolor", "sit", "amet"}]

