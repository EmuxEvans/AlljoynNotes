
Defines the members of the interface. There are 3 types:
- Methods (that can be invoked)
- Properties (values that can be retrieved, and if not read-only also set)
- Signals (events you can listen to)

### Method
```xml
 <method name="Search">
      <arg name="queryText" type="s" direction="in"/>  <!-- Input parameter : Search string -->
      <arg name="maxCount" type="q" direction="in"/>   <!-- Input parameter: Max results as UInt16 -->
      <arg name="searchResults" type="as" direction="out"/>  <!-- output: Search results as a string array -->
  </method>
```


### Property
```xml
    <property name="Temperature" type="d" access="read">
      <description language="en">The temperature measured by the sensor.</description>
      <annotation name="org.freedesktop.DBus.Property.EmitsChangedSignal" value="true"/>
      <annotation name="org.alljoyn.Bus.Type.Units" value="degrees Celcius"/>
      <annotation name="org.alljoyn.Bus.Type.Min" value="−273.15"/>
      <annotation name="org.alljoyn.Bus.Type.Max" value="1000"/>
    </property>
```
access: optional. Values: `read`, `readwrite`.

Annotations (optional): 
- `org.freedesktop.DBus.Property.EmitsChangedSignal` means this will be emitting the changed signal when the value changes . 
- `org.alljoyn.Bus.Type.Units` for units. Use SI Units where possible.

### Signal

### Naming

Interfaces have names with type STRING, meaning that they must be valid UTF-8. However, there are also some additional restrictions that apply to interface names specifically: 
- Interface names are composed of 1 or more elements separated by a period ('.') character. All elements must contain at least one character. 
- Each element must only contain the ASCII characters "[A-Z][a-z][0-9]_" and must not begin with a digit. 
- Interface names must contain at least one '.' (period) character (and thus at least two elements). 
- Interface names must not begin with a '.' (period) character.
- Interface names must not exceed the maximum name length.

Interface names should start with the reversed DNS domain name of the author of the interface (in lower-case), like interface names in Java. It is conventional for the rest of the interface name to consist of words run together, with initial capital letters on all words ("CamelCase"). Several levels of hierarchy can be used. It is also a good idea to include the major version of the interface in the name, and increment it if incompatible changes are made; this way, a single object can implement several versions of an interface in parallel, if necessary. 

For instance, if the owner of example.com is developing a D-Bus API for a music player, they might define interfaces called com.example.MusicPlayer1, com.example.MusicPlayer1.Track and com.example.MusicPlayer1.Seekable. 

D-Bus does not distinguish between the concepts that would be called classes and interfaces in Java: either can be identified on D-Bus by an interface name. 



References:
http://dbus.freedesktop.org/doc/dbus-specification.html#message-protocol-names
https://wiki.allseenalliance.org/irb/interface_design_guidelines_1.1
https://wiki.allseenalliance.org/irb/xmlv2
