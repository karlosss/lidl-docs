##############
The background
##############

So far we have learned some basic example of *LI-DL*. Now it should be the correct time to look into how it *actually* works.

Probably the most important concept is that the compiler compiles the code *exactly* as it is. The code is evaluated at runtime. Therefore, the compiler has no symbol table because it just does not need any. Let's look at an example of the compiled *LI-DL* code::

    PROGRAM = Program()                                                                                                                        
                                                                                                                                                                                         
    PROGRAM.add(ObjectFactory((0, 4), "Argument").set_property((1, 8), "value", GeneratorFactory((1, 16), [[Colon((1, 18), Integer((1, 17), 5), Integer((1, 19), 10)), Variable((1, 23), "LOWER_ASCII")]])))                                                                                                                                                                                                  
    PROGRAM.add(ObjectFactory((3, 4), "Student"))                                                                                                                                                        

    PROGRAM.run()

(Import statements are left out.)

Do you recognize the code a bit? It is the first test case from the previous chapter. You might probably understand the builder pattern to create the :code:`Argument` object. But what all these random numbers stand for? They are the line-column position of the according statements in your *LI-DL* code. The runtime needs them so that in case an error occurs, it can inform you of the line and column which caused the error. It should help to fix the problem more smoothly.

The second interesting thing is the variable :code:`LOWER_ASCII`. As you can see, the compiler just created a :code:`Variable` object with the string describing the name of the variable *and that's it*. Try modifying the variable name a bit - the code will still compile, because the compiler just does not care.

Lastly, but not leastly, it shall be mentioned that until the :code:`run()` method is called, nothing is actually executed. Therefore, the evaluation of the bytecode might resemble a JIT (just-in-time) compilation and execution, similar (for example) to Bash interpreter. The compilation only catches syntax errors, the rest is left for the runtime.

Another part of the *LI-DL* manifesto is that it shall never produce an invalid Bash script. It takes care of escaping all the "problematic" characters (such as :code:`$` or quotes), but also it tries to generate a set of unique file names in a directory. Sure, sometimes it is just *not* possible to generate a valid script, for example if one tries to create two files with exactly the same name (giving the *LI-DL* no option to variate). This will result in an error during the runtime.

The last thing which you have not seen yet is the generated Bash script. It is not one among the nicest ones, but to be honest, have you ever seen something *nice* in Bash?::

    set --
    root=$(pwd)
    cp -- "$SCRIPT_PATH" "$(printf -- '\x53\x74\x75\x64\x65\x6e\x74' )"
    chmod -- u+x "$(printf -- '%s' "${root}")"
    chmod -- u+x "$(printf -- '%s\x2f\x53\x74\x75\x64\x65\x6e\x74' "${root}")"
    source "$(printf -- '%s\x2f\x53\x74\x75\x64\x65\x6e\x74' "${root}")" "$(printf -- '\x70\x72\x78\x7a\x79\x63\x68\x66' )" <<< ""

Now it should be clear what is going on in the background of *LI-DL*. After a brief explanation of syntax in the next chapter, you should be ready to actually start learning *LI-DL*.

