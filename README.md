Sketchboard JSON
================

Project describes JSON document types that can be exported from https://sketchboard.me.

Class Diagram JSON
------------------

### Creating Class Diagrams

Create Class Diagram on https://sketchboard.me. Diagram elements are identified as classes if class icon is used on Sketchboard.io.

#### Class element from UI Context menu
![Class Element from UI Context Menu](img/class-icon.png)

#### Class element from library
![Class Element from Library](img/class-icon-from-library.png)

All connections between in version 1 are identified as relationships.

### Version 1 (experimental)

Version 1 exports class names, stereotypes and relationships related to classes. 

![Sample Sketch Class Diagram](img/sample-sketch.png)

```json
[{
  "name":"StakeHolder",
  "methods":["fullName(): String"],
  "attributes":["firstName: String","lastName: String","role: Int"],
  "relationships":["Project","Feature","Requirement"]
},{
  "name":"Project",
  "attributes":["name"],
  "relationships":["Feature"]
},{
  "name":"Feature",
  "stereotype":"interface",
  "relationships":["Requirement"]
},{
  "name":"Requirement"
},{
  "name":"FeatureImpl",
  "relationships":["Feature"]
}]
```
