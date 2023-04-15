# Generics-Java-Concept
This repository provides a comprehensive guide to Generics in Java, covering fundamental concepts such as type parameters, wildcards, and generic methods. It includes examples and explanations to help both beginners and experienced Java developers implement Generics effectively.

# Generics: Raw Type
## The Idea
Because support for generics did not exist prior to JDK 5 <br />
it was necessary to provide some transition path from old pre-generic code.

this transition path had to enable pre-generic code to remain functional<br />
while at the same time being compatible with generics.

To Enable this transition path gave birth to a concept called `The Raw Type of a Class`. <br />
Such that a Generic class could be used as if it's a normal class<br />
and also it could still be used as a generic class.

<img src="./ReadMe-Images/raw-generics-A.svg" style="width:600px; height:auto" alt="Showing The Raw Type of a Generic Class A ">
<img src="./ReadMe-Images/raw-generics-B.svg" style="width:600px; height:auto" alt="Showing The Raw Type of a Generic Class B ">

First Thing to know when creating a Raw Type,<br />
notice that no type argument are specified when a Gen Object is created.<br />
In Essesnce, this creates a Gen Object whose type `T` is replaced by `Object`. 

Secondly, because at run-time, the type of ob is `Object`,<br />
there must be a cast to obtain its value as a type `double`

## The Conflict: Bypassing Type Safety
<img src="./ReadMe-Images/raw-generics-conflict.svg" style="width:600px; height:auto" alt="Showing Conflicts dealing with Raw Types ">

A Raw Type is not Type Safe. Thus, the variable of a raw type<br />
can be assigned a reference to any type of Gen Object
for example `raw = iOb;`

Also the variable of a specific Gen type <br />
can be assigned a reference to a raw Gen Object. e.g `strOb = raw;`

Lets have a Clear look
<img src="./ReadMe-Images/raw-generics-conflict-A.svg" style="width:600px; height:auto" alt="Showing Conflicts dealing with Raw Types A ">

Because `strOb` is of type `Gen<String>`, it is assumed to contain a string.<br />
However, after the assignment, the object referred to by strOb contains a Double.<br />
Thus at run time when an attempt is made to assign the contents of strOb to str,<br />
a run-time error results because strOb now contains a Double.

<img src="./ReadMe-Images/raw-generics-conflict-A.svg" style="width:600px; height:auto" alt="Showing Conflicts dealing with Raw Types A ">

Here, A Generic Reference is assigned to a raw reference variable.<br />
`raw` now refers to an object that contains and Integer Object.<br />
But the case assumes that it contains Double.<br />
this error cannot be prevented at compile time, rather it causes a run time error.

## The Warning
Because of the potential for danger inherent in Raw Types,<br />
`Javac` displays `Unchecked warnings` when a Raw Type is used <br /> 
in a way that might jeopardize type safety.

## End Note
You should limit the use of raw types to those cases<br />
in which you must mix legacy code with newer, generic code.<br />
Raw Types are simply a transitional feature<br />
and not something that should be used for new code.




# Generics: Class Hierarchies
Generic class can be a part of a class hierarchy<br />
in just the same way as a non-generic class.

The Key Difference between Generic and Non-Generic Hierarchies<br />
is that in a generic hierarchy, any type argument needed by a generic superclass<br />
must be passed up the hierarchy by all subclasses.

This is similar to the way that constructor arugments must be passed up a hierarchy<br />
or how class implementation of a Generic interface,<br />
must pass up type parameters needed by the interface.

<img src="./ReadMe-Images/generic-class-hierarchy.svg" style="width:600px; height:auto" alt="Showing Generics Class Hierarchy example A">

Similar to normal class hierarchies, 
concepts like `instanceOf`, `casting` and `method Overidding` still holds.
Typical Right!!

<img src="./ReadMe-Images/generic-class-hierarchy-instanceOf.svg" style="width:600px; height:auto" alt="Showing instanceOf Concept in Generics Class Hierarchy">

<img src="./ReadMe-Images/generic-class-hierarchy-casting.svg" style="width:600px; height:auto" alt="Showing Casting Concept in Generics Class Hierarchy">




# Generics: Type Inference

Basically, When using Generics, we can use shorter syntax.
which helps us not to repeat our selves.
This is where Type Inference comes in. Have a look.

<img src="./ReadMe-Images/generic-class-hierarchy-typeInferenceA.svg" style="width:600px; height:auto" alt="Showing Type Inference A ">

<img src="./ReadMe-Images/generic-class-hierarchy-typeInferenceB.svg" style="width:600px; height:auto" alt="Showing Type Inference B ">





# Generics: Implementation (Erasure)



