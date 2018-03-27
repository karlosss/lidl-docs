#########
Generator
#########

Generators are bread and butter of *LI-DL*. They are used for generating random strings from given characters of given length. You can think of generators like of regular expressions vice versa: instead of describing a real text with a regular expression, you write the expression and *LI-DL* generates for you a random string that matches.

Generators not only serve for generating random string as described above, but also bring some kind of "loops" to *LI-DL*. A generator can cause another generator to be invoked repeatedly, resulting in generating a bunch of strings matching the same criteria. This might be useful for generating dummy configuration files (like ``/etc/passwd`` in the quickstart).

A generator consists of two parts: definition of the count and definition of the source. A count might be an integer or something that yields an integer (a range, a choice) and the source might be anything. Strings, integers and floats will be just concatenated several times, several elemets from an alphabet will be randomly chosen to create a string, and ranges, generators and choices will be asked to produce a value several times and the results will be concatenated together.

The source part of a generator will be invoked as a whole in each "iteration". This emulates the concept of local variables (although there is actually nothing like that in *LI-DL*). For a usage, see the examples below.


Syntax
------

A generator is enclosed in square brackets (``[`` and ``]``) and its two parts are separated by a comma (``,``). The first part denotes the count, while the other denotes the source.
::

    [5, "Hello!"]

    [10, 
         [10, "This sentence will be printed 100 times.\n"] + 
         "After each 10 sentences, this will appear.\n"
    ]


Examples
--------

A generator to generate a text of 10 lorem ipsum words (note the trick to get rid of the trailing space at the end of the text)::

    [9, {"lorem ", "ipsum ", "dolor ", "sit ", "amet "}] + 
    [1, {"lorem", "ipsum", "dolor", "sit", "amet"}]

A generator to generate from 30 to 50 pairs of same integers from 0 to 99, separated by ``:``. (note the trick to store the number and reuse it later - the generator source is invoked in each iteration over again)::

    [30:50, (tmp=0:99) + ":" + tmp + "\n"]

