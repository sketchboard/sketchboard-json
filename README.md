Sketchboard JSON
================

Project describes JSON document types that can be exported from https://sketchboard.me.


Creating Class Diagrams
-----------------------

Create Class Diagram on https://sketchboard.me. Diagram elements are identified as classes if class icon is used on Sketchboard.io.

Methods and attributes are defined in section after stereotype and class name. Methods are distinguished from attributes if value contains parenthesis according to UML method declaration. Section order doesn't matter for attributes and methods as long as those are after stereotype and class name.

Class syntax:
```
StakeHolder
--
firstName: String
lastName: String
role: Int
--
fullName(): String
```

#### Class element from UI Context menu
![Class Element from UI Context Menu](img/class-icon.png)

#### Class element from library
![Class Element from Library](img/class-icon-from-library.png)

All connections between classes in version 1 are identified as relationships.


Class Diagram JSON
------------------

### Version 1 (experimental)

Version 1 exports class names, stereotypes and relationships related to classes. 

![Sample Sketch Class Diagram](img/sample-sketch.png)

```json
[{
  "name":"FeatureImpl",
  "relationships":[{
    "name":"Feature",
    "type":"-|>"
  }]
},{
  "name":"Requirement"
},{
  "name":"Project",
  "relationships":[{
    "name":"Feature",
    "type":"->"
  }]
},{
  "name":"StakeHolder",
  "methods":["fullName(): String"],
  "attributes":["firstName: String","lastName: String","role: Int"],
  "relationships":[{
    "name":"Requirement",
    "type":"->"
  },{
    "name":"Project",
    "type":"->"
  }]
},{
  "name":"Feature",
  "stereotype":"interface",
  "relationships":[{
    "name":"Requirement",
    "type":"->"
  }]
}]
```
