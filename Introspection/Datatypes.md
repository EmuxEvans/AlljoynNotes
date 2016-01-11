http://dbus.freedesktop.org/doc/dbus-specification.html#type-system

## List of data types in Introspection XML
| Type  	|  	|                          	|
|--------	|-----	|---------------------------------------------------------------------------------------|
| Int16  	| `n` 	| A signed 16-bit integer. Valid values are (+/-) 32,767.                         	|
| UInt16 	| `q` 	| An unsigned 16-bit integer. Valid values are 0 to 65,535.                       	|
| Int32  	| `i` 	| A signed 32-bit integer. Valid values are (+/-) 2,147,483,647.             	|
| UInt32 	| `u` 	| An unsigned 32-bit integer. Valid values are 0 to 4,294,967,295.                	|
| Int64  	| `x` 	| A signed 64-bit integer. Valid values are (+/-) 9,223,372,036,854,775,807. 	|
| UInt64	| `t`	|An unsigned 64-bit integer. Valid values are 0 to 18,446,744,073,709,551,616. 	|
| Double        | `d` | A double-precision (64-bit) IEEE 754 floating point value. |
| Byte          | `y` | A single byte (a string of eight binary digits). |
| String        | `s` | A UTF-8 encoded string |
| Boolean       | `b` | A boolean value. |
| Array         | `a` |  Compound data type. Must be followed by datatype. Ie an integer array: `ai` |
| Struct        | `(`...`)` | Ie a struct of string, bool and int: `(sbi)` |
| Dictionary    | `{`...`}` |  For instance string,int dictionary: `{si}` |
| Variant       | `v` |  In .NET-speak an 'object' of any type. |
| DBUS Object path | `o` |  Currently not supported by Microsoft's code generator. |

An array can be of any type, such as this array-of-struct-with-two-int32-fields `a(ii)` or
this array of array of integer `aai`.
        
Structs can be nested, so for example a struct containing an integer and another struct `(i(ii))`.

Dates: Dates are not part of the specification. Can be solved with Annotations (see Annotations). 
Typically Int64 is used as milliseconds since 1970 in UTC format.


