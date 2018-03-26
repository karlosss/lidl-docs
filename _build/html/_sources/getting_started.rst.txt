###############
Getting started
###############

*LI-DL* is currently embedded in the *LearnShell* project and therefore the compiler is accessible via the web application. To access the *LI-DL* field, go create (or edit) a problem, in there go create (or edit) a test and scroll down to *LI-DL* generator. This is the field where *LI-DL* code should go in.

Say you have a really simple problem. You want to write a Bash script which prints its first positional parameter. Therefore, a correct solution could look for example like this::

    printf -- "$1"

When generating the input data, we could make four test cases: the first one will contain only lowercase characters (to see if the script works at least a bit), the second one could contain more than one parameter (to check if :code:`$1` is used and not for example :code:`$@`), the third one could contain some whitespaces (to check for quotation) and the last one could look like an option (to check for :code:`--`).

For the first test case, we need to specify that we want one positional parameter, consisting of let's say from 5 to 10 lowercase characters. *LI-DL* introduces constructions called *objects* to represent the units of test data (an object can be a shell variable, a parameter, a file, a directory, and so on) and *generators* (for strings) or *ranges* (for integers) to generate random stuff. Let's go ahead and write our first *LI-DL* code::

    Argument {
        value = [5:10, LOWER_ASCII]
    }
    Student {}


Let's explain it a bit. :code:`Argument {...}` is the definition of an :code:`Argument` object, which causes a positional parameter to be generated. The objects in *LI-DL* have *properties* and sometimes can hold another objects (e. g. a :code:`Directory` object can contain :code:`File` objects, causing a directory including those files to be generated). Some of the properties are mandatory, some have a default value, and some might change the behavior of an object. The :code:`Argument` object has a mandatory property called :code:`value` which specifies the value of the argument. It could be a string or an integer (*LI-DL* of course has those data types as well) but it will cause the argument to be constant and that is not what we want here. We need a random string here. And that is where *generators* come into play.

A *generator* is a data type in *LI-DL* which serves for generating random strings. It is written as :code:`[... , ...]`. The first part (let's call it first parameter) is a count (might be an integer or a range) and specifies how many characters will be used in the string. And the second parameter is a collection where the generator takes the characters from (it might be a constant string, an *alphabet* which will be explained later, or even another generator, causing it to be invoked repeatedly).

The syntax of a *range* is quite simple: :code:`X:Y`, where :code:`X` is the lower bound and :code:`Y` is the upper bound (both are included in the range). So our :code:`5:10` range upon request yields an integer from 5 to 10 (both included) with a uniform probability.

To define an alphabet with characters :code:`a`, :code:`b` and :code:`c`, we would write :code:`{"a","b","c"}`. It would be quite annoying to write the whole lowercase alphabet so *LI-DL* has some builtins. One of them is exactly the lowercase alphabet. Therefore, all what needs to be done is to use the variable :code:`LOWER_ASCII`.

And this is almost it. You might be wandering what the :code:`Student {}` means. Maybe you realized it is an object. The meaning is that it denotes where in the directory structure the submitted script will be placed. If located inside a :code:`Directory` object, the submitted script will be copied to there. In our problem, it actually does not matter, so let's start in the home directory.

Now click on the compile button and if everything goes right, you should see twice *OK*. Click on save and you are ready to send some submission to see *LI-DL* in aciton. If you reveal the input data hint, you should see your string in the arguments section.

Alright? Let's go to the second part. We need to generate two arguments now. Since the arguments are often similar (a lot of natural numbers, for example), :code:`Argument` object has a property `count`, meaning how many of those arguments are meant to be generated. So this will be our code::

    Argument {
        count = 2
        value = [5:10, LOWER_ASCII]
    }
    Student {}

I believe no more explanation is needed. Again, don't forget to take the input data hint and see the change.

Let's go for the third one and explore a new part of *LI-DL*, *operators*. We actually already encountered an operator :code:`:`, taking two integers and returning a range. Now, we need one more: :code:`+` for string concatenation.

Since a generator yields a string, it could be concatenated with another string (or a generator, or even an integer or a range, *LI-DL* automatically converts the integer to a string). Let's say we want 3 lowercase letters, 3 spaces and 3 uppercase letters::

    Argument {
        count = 1
        value = [3, LOWER_ASCII] + "   " + [3, UPPER_ASCII]
    }
    Student {}

Strings in *LI-DL* are similar to strings in Python, making no difference between single and double quotes. They also support some metacharacters like :code:`\n` for newline or :code:`\x40` to write a :code:`@` in a cool way.

As you can see, we specified :code:`count = 1` here. If we did not mention it at all, the meaning would stay the same - this is an example of a property with default value (being in this case :code:`1`).

The last test case should be not surprising in any way, since we already know everything. Maybe try to write a code on your own, let's just include an option how to do it for verifying purposes::

    Argument {
        value = "-" + [1, LOWER_ASCII]
    }
    Student {}

How do you like *LI-DL* so far?
