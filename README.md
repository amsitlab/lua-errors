
**errors** is an error library for lua using oop paradigm.

# Example #

* using errors on current _ ENV
```lua
local errors = require "errors"
```

* handle specific error:

```lua
local errors = require "errors"
local raise = errors.Runtime("Runtime error")
if raise:is(errors.Arithmetic) then
   error(raise "Thats errors.Arithmetic" )
elseif raise:is(errors.IO) then
   error(raise "Thats errors.IO")
elseif raise:is(errors.Runtime) then
   error(raise "Thats errors.Runtime")
end
```

output:
```
raise by [errors.Error]:
Thats errors.Runtime
stack traceback:
        stdin:1: in main chunk
        [C]: in ?
raise by [errors.Runtime]:
Runtime error
stack traceback:
        stdin:1: in main chunk
        [C]: in ?
```

* formatting error message.
```lua
local file = "path/to/file.txt"

local err = errors.FileNotFound "No such file: {filename}" % {filename = file}
print(err)
```

output:
```
raise by [errors.FileNotFound]:
No    such file: path/to/file.txt
stack traceback:
        stdin:1: in main chunk
        [C]: in ?
```

# Install #
you can use [luarocks](https://luarocks.orh)
```luarocks install errors
```

# Project dependecies #
This project use excellent library
   - [classy](https://github.com/siffiejoe/lua-classy)

# Licanse #
   License is same as Lua 5.3 license.
