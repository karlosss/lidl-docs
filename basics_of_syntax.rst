################
Basics of syntax
################

You probably already have an idea how *LI-DL* syntax works, but let's extend it a bit.

The most important thing is that *LI-DL* does not use semicolons (that is this ugly symbol: :code:`;`). Say hurray!

(Actually, this means the it is never-ever possible to have multiple statements on one line and you cannot put linebreaks wherever you want. But nobody likes semicolons, right?)

In *LI-DL*, there are two (meaningful) statements: variable assignment and object declaration. Variable assignment has the same syntax as in Python::

    variable_name = its_value

where the value might be a string, a number, another variale, an alphabet, or even a generator or a range. There is one thing which you might find weird, but it actually enables a lot of stuff. If you assign a non-deterministic data type (generator or range) into a variable, the non-deterministic data type is request to generate a value (usually an integer or a string) and this value is stored into the variable. If you would like to assign a generator itself into a variable, then I have bad news for you. You need to use copy and paste. Sorry.

*LI-DL* program has a single scope for variables. There is actually no reason to have more than one scope, although defining a new variable inside an object and then using it outside might look a bit confusing. But nothing prevents you to redefine the variable outside and if you want to, you can use the value assigned to it before. *LI-DL* provides a lot of freedom here.

The exaple declaration of an object looks like this::

    ObjectName {
        property = value
        another_property = another_value
        NestedObject {
            property_nested = value_nested
        }
    }

The opening bracket must be on the same line as the object name. Sorry, ANSI C programmers.

Let's have look at expressions now. *LI-DL* has a few binary operators (like :code:`+` or :code:`:` which we have already used). There are no unary operators at the moment (yes, even minus for negative integers, which is sometimes quite annoying). Also, there is a comma separator.

*LI-DL* allows a line break after both binary operators and the comma operator because it is clear that the statement must go on with an expression, so *LI-DL* looks for it on the next line.
This might make the code more readable, as there are often quite complex string concatenations.

You can put spaces and tabs wherever you wish. An empty line is also okay.

The operators have priority, which can be changed using parentheses (that are :code:`(` and :code:`)`). An opening parenthesis also allows a linebreak after it. So do the square brackets of generators and curly brackets of alphabets.

Now the syntax of *LI-DL* shall be clear. Now it is time for a more complex example and you should be ready to start writing generators on your own.

