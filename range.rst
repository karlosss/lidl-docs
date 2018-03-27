#####
Range
#####

This covers both integer and float range, as they are both pretty much the same.

Those constructions are generators of random numbers from a given range. It always has a lower bound and an upper bound and generates a number from between those bounds. If both bounds are integers, then the range is considered an integer range, and therefore yields integers. If at least one bound is float, then the range is considered a float range and yields floats. Both bounds are considered to be a part of the interval.

Upper bound must be always greater than the lower bound. (Or, they might be equal, but why not to write a simple integer/float instead?)

Remember, *LI-DL* has no negative numbers. If you need (pseudo)negative numbers, just concatenate the number with string ``-``. If you need to generate sometimes a positive and sometimes a negative number, use a choice ``[0.5, "-"]`` (or whatever you want the probability to be).

Syntax
------

A range is built with the help of ``:`` operator::

    5:10
    0.5:2

Examples
--------

Integer ranges::

    5:10
    0:50

Float ranges::

    0.5:2
    2:3.5
    0.5:1.5

