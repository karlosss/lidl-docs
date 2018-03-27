######
Choice
######

A choice is a construction which upon request randomly chooses an item from a given collection.

The items might be defined not to have equal probability to be chosen. They might be of arbitrary type. Strings, integers and floats are yielded as they are, other data types (generators, ranges, choices and alphabets) are asked to produce an item and that item is returned.

The probability definition might be a bit tricky. Similarly to generators, all items come in pairs, whose meaning in this case is the probability and the actual item (in this order). If the sum of probabilities of all items is less than 1, the choice has a chance of producing an empty string (with probability equal to 1 minus the sum of all probabilities). If the total probability is equal to 1, then it should be clear. And if it is greater than 1, *LI-DL* normalizes it to 1. The definition of the probability can be omitted, in which case 1 is assumed (whatever its meaning at the moment is).

Probabilities are integers, floats, or whatever yields an integer or a float. The items might be of arbitrary type, as described above.


Syntax and examples
-------------------

Choice's syntax is very similar to generators: it is enclosed in square brackets (``[`` and ``]``). The items of the pairs are separated by commas (``,``) and the pairs are separated from each other by vertical bars (``|``). In case the probability is omitted, there is only one item in the "pair", and therefore no comma is needed.

70 % to yield ``a`` and 30 % to yield ``b``::

    [0.7, "a" | 0.3, "b"]

70 % to yield ``a`` and 30 % to yield ``b`` again, with the use of automatic normalization::

    [7, "a" | 3, "b"]

70 % to yield ``a`` and 30 % to yield an empty string. The only thing distinguishing this from a generator is float in the probability count::

    [.7, "a"]

100 % to yield ``a``. This is actually not a choice, but a generator, since 1 is an integer. But if you think about it for a moment, you realize that yielding an item with 100% probability and yielding an item once is exactly the same::

    [1, "a"]

If you try do the thing above with the use of normalization, you will fail, because this is a true generator. However, if you used ``5.0`` instead of ``5``, it would work as a choice::

    [5, "a"]

To choose from several options with equal probability, you can do this. Think of the underlying mathematics for yourself::

    ["alpha" | "beta" | "gamma" | "delta"]

The probability of delta here is 12.5%::

    ["alpha" | "beta" | "gamma" | 0.5, "delta"]

Choice in a choice might also be used. The probabilities are 25 % each for ``alpha``, ``beta`` and ``gamma``, while the remaining 25 % is equally distributed between ``a``, ``b`` and ``c``::

    ["alpha" | "beta" | "gamma" | ["a" | "b" | "c"]]

