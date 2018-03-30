##################################
Variable (*LI-DL* auxiliary agent)
##################################

As you for sure know, variable itself is not a data type. But there was nowhere else in the documentation to place this.

A variable is a key in the symbol table during the runtime. Its associated value might be a string, an integer, a float, or an alphabet. The remaining data types and object might not be stored in a variable.

Variable assignment is done by operator ``=``. Variable reading is done by just writing its plain name.

Although only data types mentioned above might be the values of a variable, actually any data type can be assigned to a variable. In case a range, a generator or a choice is assigned, a value is produced and that value is stored into the variable. It might seem a bit confusing.

Of course, a value of a variable might be copied to another variable. This is done by putting the source variable on the right side of the operator ``=``. All copies made this way are deep. There is no shallow (reference) copying in *LI-DL*.

There is just a single scope in *LI-DL*. A variable might be (re)defined absolutely everywhere and the (re)definition will have global impact.

Variable assignment returns the assigned value.

Syntax
------

A variable is just a plain string without quotes. It might consist of lowercase characters (arbitrarily) and uppercase characters, digits and underscores as long as they are not the first character of the name. ALL CAPS names are reserved for builtin constants and names starting with a capital letter are reserved for objects. 

Operator ``=`` is used for the actual assignment. The right-hand side might be arbitrarily complicated::

    a = "hello"
    b = a + a
    c = (a="hi") + b

Examples
--------

Variable ``tmp`` is defined inside a generator. Variable ``x`` will have the same value as ``tmp`` in the last pair of generated integers, as it was the last time the generator source was invoked::

    [30:50, (tmp=0:99) + ":" + tmp + "\n"]
    x = tmp

