# llsecurecodingrulejavaserialization


## Understand Java object serialization
Serializable class:
- Save and restore fields of each object
- Allow classes to evolve by adding fields or superclasses
A serializable class can
- Declare which of its fields are saved or restored
- Write and read optional values and objects
By default non-transient and non-static fields are serialized.
```
FileOutputStream f = new FileOutputStream("tmp");
ObjectOutput s = new ObjectOutputStream(f);
s.writeObject(new Bicycle());
s.flush();
```


Deserialization 
```
FileInputStream in = new FileInputStream("tmp");
ObjectInputStream s = new ObjectInputStream(in);
Bicycle bike = (Bicycle)s.readObject();
```


##### callback order
During serialization, the `writeReplace` method is executed first. If present, the `writeObject` method operates on the
replacement object.
`Deserialization` callback methods are invoked in the order.
