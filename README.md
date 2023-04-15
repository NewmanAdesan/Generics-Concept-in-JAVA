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

## The Conflict
<img src="./ReadMe-Images/raw-generics-conflict.svg" style="width:600px; height:auto" alt="Showing Conflicts dealing with Raw Types ">

A Raw Type is not Type Safe. Thus, the variable of a raw type<br />
can be assigned a reference to any type of Gen Object
for example `raw = iOb;`




## The Warning
