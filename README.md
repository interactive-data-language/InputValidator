# InputValidator

Routine that can be used to perform input validation for any routine to ensure that parameters are present or a certain type. You can specify each possible types that the data value can represent and optionally require that the value have all of the types. Here are the generic types that can be used for any variable:

- required : If set, the value must be present and defined.

- array    : If set, value supplied must be an array.

- number   : If set, value supplied must be a number.

- file     : If set, the value must represent a valid file on disk.

This routine uses IDL's `isa` function to make the comparison so, in addition to the types above, you can specify anything else that can pass as an argument to the `isa` routine. Some additional examples of types are are: byte, int, long, float, hash, orderedhash, enviraster, graphicswin. The addition arguments can be any IDL-specific data type or it can also be the type of object such as idlgrwindow or any named, custom object.

## Examples

See the PRO code on descriptions of the keywords.

### Validate that an argument is present and defined:

```idl
inputValidator, hash('nameOfArg', 'required')
```

Note that this means the variable is not undefined (i.e. defined in the IDL code or passed in as a parameter). A variable defined as `!NULL` will still pass because that is a valid value of a variable.

### Validate that an argument is a string array and present

```idl
inputValidator, hash('nameOfArg', ['string', 'array', 'required'])
```

### Validate that an argument, if present is a double array

```idl
inputValidator, hash('nameOfArg', ['double', 'array'])
```

## License

Copyright (c) 2018 Harris Geospatial Solutions, Inc.

Licensed under MIT, see LICENSE.txt for more details.
