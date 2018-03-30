##################
Objects in general
##################

Objects are the actual things which get translated to Bash. They describe the input structures - files, positional parameters, stdin, and so on.

Objects have *properties* and sometimes can hold another objects. A property is a further configuration or a setting how an object should behave (for example, a file needs a name) and an example meaning of another objects within an object could be files contained in a directory.

Properties always have a name and a value. This makes them similar to object attibutes in programming languages. Certain objects have certain properties allowed, along with allowed data types of their values. Some of the properties are required, some have a default value. Some must be defined before others. See the documentation for each object to check what are the constraints in specific cases.

Similarly to parts of generators, a property requiring a certain data type can take anything which yileds the correct data type. For example, a name of a file can be specified by a generator, because it yields a string and a string is a valid data type for a filename.

There is one global constraint. If you want an object to have both properties defined and objects included, all the properties must be defined first. This is for easier object management in the *LI-DL* runtime framework and I believe that this constraint will have no real impact on the user.

It is not possible to define custom objects, there are only builtin objects.

Syntax
------

An object name starts with a capital letter and is followed by a lowercase letter. Generally, CamelCase notation is used for object names. An object's body is enclosed in curly brackets (``{`` and ``}``). Within those brackets, properties can be defined as ``property = value`` (same syntax as variable assignment), and another object can be included following these syntax rules recursively.

The opening curly bracket must be at the same line as the name of the object.
::

    ObjectName {
        property = value
        another_property = another_value
        NestedObject {

        }
        AnotherNestedObject {
            prop = val
        }
    }

Examples
--------

This models a directory with several files. I believe that the meanings of used properties and objects are self-explanatory::

    Directory {
        name = "dir"
        File {
            name = "A"
        }
        File {
            name = "B"
        }
        File {
            name = "C"
        }
    }

This would not work, as there is an object defined before a property::

    Directory {
        File {
            name = "A"
        }
        name = "dir"
        File {
            name = "B"
        }
        File {
            name = "C"
        }
    }

