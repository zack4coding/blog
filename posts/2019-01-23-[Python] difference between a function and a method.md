
FOR OOP In general: methods are functions that belong to a class, functions can be on any other scope of the code so you could state that all methods are functions, but not all functions are methods
A function is a piece of code that is called by name. It can be passed data to operate on (i.e. the parameters) and can optionally return data (the return value). All data that is passed to a function is explicitly passed.

A method is a piece of code that is called by a name that is associated with an object. In most respects it is identical to a function except for two key differences:

A method is implicitly passed the object on which it was called.
A method is able to operate on data that is contained within the class (remembering that an object is an instance of a class - the class is the definition, the object is an instance of that data).
(this is a simplified explanation, ignoring issues of scope etc.)

FOR Python
This is the new class hierarchy for functions and methods:
```
              object
                 |
                 |
          base_function
         /       |     \
        /        |      \
       /         |   defined_function
      /          |        \
cfunction (*)    |         \
                 |       function
                 |
           bound_method (*)
```
The two classes marked with (*) do not allow subclassing; the others do.

There is no difference between functions and unbound methods, while bound methods are instances of bound_method.

References
[stackoverflow](https://stackoverflow.com/questions/155609/whats-the-difference-between-a-method-and-a-function?rq=1)

[PEP 575 -- Unifying function/method classes](https://www.python.org/dev/peps/pep-0575/#withdrawal-notice)
