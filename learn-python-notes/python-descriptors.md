# Python Descriptors [Notes]

[Introduction to Python Descriptors](https://developer.ibm.com/tutorials/os-pythondescriptors)
  - Descriptors create managed attributes
  - Managed attributes either... 
    - protect an attribute from changes 
    - OR
    - automatically update the values of a dependant attribute
  - Descriptors protocol (de-scriptor)
    - Specifies what happens when a model has an attribute it references
    - Set, Get, Delete
    - Python does not have a "private variables concept"
    - Descriptor protocol achieves something similar to the concept of private variables
    - Descriptor: object attribute; has binding behavior; access to attributes is overriden by methods customized in descriptor protocol
      - Descriptor function names: __get__, __set__, & __delete__
    - "It is important to note that descriptors are assigned to a class, not an instance. Modifying the class overwrites or deletes the descriptor itself, rather than triggering its code."
    - TODO: finish