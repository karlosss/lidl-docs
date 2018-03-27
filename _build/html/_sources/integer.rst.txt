#######
Integer
#######

An Integer is a positive integer number. Integers are used as repetition bounds, possibly probability constants, and literals. Unlike many programming languages, *LI-DL* has no negative numbers, as there is no unary ``-`` operator. The workaround is to contatenate the ``"-"`` string with an integer. 

There are no mathematical operators present in *LI-DL*. Therefore, ``1 + 1`` results in a string ``"11"`` and ``1 - 1`` is an error. This behavior might be a bit counter-intuitive, so beware of that.

Syntax
------
Hey, do you really need this? Ok, there you go::

    6
    42
    69


Examples
--------
Assigning integer to a variable::

    var = 42
    another_var = 0

