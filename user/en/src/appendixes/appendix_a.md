# Appendix A. Naming Multiple Objects

A naming pattern is used to dynamically create the names of new objects or new special objects
using the actions New Multiple and New Special Multiple, respectively, using on a simple syntax.
The naming pattern is composed by static and dynamic sections. In the static section, any string
of characters can be placed, with the exception of the characters `[` and `]`, while in the dynamic
part only the pre-defined functions listed below can be placed.

* `[sequence(a,z)]` Generates an alphabetic ascending lowercase sequence that begins in the parameter a (a-z) to the parameter z (a-z)
* `[sequence(A,Z)]` Generates an alphabetic ascending uppercase sequence that begins in the
parameter A (A-Z) to the parameter Z (A-Z)
* `[sequence(n,m)]` Function that generates a numeric ascending sequence that begin ins the
parameter n (0...) to the parameter m (0...)
* `[value(Object Id,Object Class Name,Attribute Name)]` Places the value of an object’s attribute, given the object id, object class name and the attribute name.

Examples of naming patterns are: `router-[sequence(1,3)]-[sequence(a,c)]`, `[value(1111,name)]-[sequence(A,Z)]`, the first pattern generates six (2*3) different names, while the second, twenty six (1*26) different names.
Depending on the combination of patterns, only a limited number of names can be generated. If the number of possible names is less than the number of objects to be created provided by the user, the objects or special objects will not be created.

## Create Multiple Mirror Ports

* `[mirror(a,b)]` Generates pairs of ports according to the specified quantity, starting from parameter a (0...) to parameter b (b > a...).
* `[multiple-mirror(a,b)]` Generates ports for a fiber optic splitter. It creates one input port 001-IN and output ports from parameter a (0...) to parameter b (b > a...).

Examples of mirrors are : `[mirror(1,10)]` this command will create 20 ports, 10 front ports and 10 back ports, 001-front, 001-back... 010-front, 010-back, the created ports will be connected as mirror ports.

`[multiple-mirror(2,5)]` this command will create one input port 001-IN and four output ports, 002-OUT(001-IN) to 005-OUT(001-IN), the created ports will be connected as a fiber optic splitter.
