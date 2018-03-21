###############
Getting started
###############

*LI-DL* is currently built in in the *LearnShell* project and therefore the compiler is accessible via the web application. To access the *LI-DL* field, go create (or edit) a problem, in there go create (or edit) a test and scroll down to *LI-DL* generator. This is the field where *LI-DL* code should go in.

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

