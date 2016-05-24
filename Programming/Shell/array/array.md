## Arrays in Shell [Back](./../Shell.md)

Arrays may be initialized with **variable[n]** notation, and to access elements with *curly bracket* notation like **$[variable[n]]**.

#### Initialization

```bash
# there is a convenient way of initializing an entire array
base64_charset=( {A..Z} {a..z} {0..9} + / = );

base64_charset=( [0]={A..Z} [1]={a..z} [2]={0..9} [3]=+ [4]=/ [5]== );
```

*Notice that: any variables can have array operations, even if they are not explicitly declared as arrays:*

```bash
#!/bin/bash

name=aleen
echo ${name[@]};        # => aleen
echo ${name[*]};        # => aleen
echo ${name[0]};        # => aleen
echo ${name[1]};        # => 

# array length
echo ${#name[@]};       # => 1
```

#### Operations

If you want to read an element from an array, you can write like this:

```bash
#!/bin/bash

array=(zero one two three);

# get a specific element in an array
echo ${array[0]};       # => zero

# get a specific element and start at a specific position
echo ${array: 2};       # => ro
echo ${array[1]: 1};    # => ne
```

If you want to read some lengths like the length of the element or of the array:

```bash
#!/bin/bash

array=(zero one two three);

# get the length of the array
echo ${#array[*]};      # => 4
echo ${#array[@]};      # => 4

# get the length of the first item
echo ${#array};         # => 4
echo ${#array[0]};      # => 4
```

Trailing Substring Extraction:

```bash
#!/bin/bash


```