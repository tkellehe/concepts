# Golfing Languages?

Some concepts I have been messing around with looking into what makes a good code-golfing language.

## Terms

* __Character__ : A length of bytes with a specified encoding.
* __Token__ : A set of __characters__ that holds meaning to the language.
* __Command__ : A __token__ with functionality.
* __State__ : Data interpreted that holds meaning to the language in which a __command__ can operate on.
* __Type__ : A specific interpretation of __state__ which can change the functionality of a __command__.

## Properties

These are properties that I have noticed that greatly reduce the number of bytes in a particular challenge.

* Make __tokens__ need as few __characters__ as possible to create smaller __commands__.
* Make a __character__ fit within a byte to reduce the number of bytes needed to create a particluar __token__, 
therein still providing a large number of single __character__ __tokens__ that only add a single byte.
* Have inferred __commands__ from other __commands__ (such as ending a loop).
* Reuse __tokens__ for other __commands__ if does nothing.
* Reduce the number of __commands__ needed to create the most __state__.
* Reduce the number of __commands__ needed to gain access to the most __state__.
* Reduce the amount of __state__ needed to do a __command__.
* Change meaning of __command__ based off of __type__ of __state__ acting upon.
* Do not add __commands__ that other __commands__ can do unless it does it in fewer bytes.
* Remove duplicate functionality between __commands__ to not waist __tokens__ (still must follow other properties though).
* Change functionality of __commands__ that have no affect ie `+-` could be inferred to mean `+.-`.
