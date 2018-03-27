#####
Float
#####

A Float is a positive decimal number. Float are used as probability constants and literals. Unlike many programming languages, *LI-DL* has no negative numbers, as there is no unary ``-`` operator. The workaround is to contatenate the ``"-"`` string with a float. 

There are no mathematical operators present in *LI-DL*. Therefore, ``1 + 1.0`` results in a string ``"11.0"`` and ``1.0 - 1.0`` is an error. This behavior might be a bit counter-intuitive, so beware of that.

Syntax
------
The decimal point is represented by a dot (``.``). If the integer or decimal part is zero, the ``0`` can be omitted (but ``0.0`` cannot be written as ``.``, it must be either ``0.`` or ``.0``).
::

    6.5
    .25
    7.


Examples
--------
Assigning float to a variable::

    var = 6.5
    another_var = .25

