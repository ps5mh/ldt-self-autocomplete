# ldt-self-autocomplete
Eclipse LDT may not autocomplete for "self", unless you specify the function parent and first param self in [documentation language](http://wiki.eclipse.org/LDT/User_Area/Documentation_Language).  
That means you should add these comments to all the instance methods to make autocompletion work for self inside these functions.
```lua
---
-- @function [parent=#YOUR_TYPE] YOUR_FUNCTION_NAME
-- @param self
```
To workaround this little inconvenience I did this.
I already discussed this [issue](https://www.eclipse.org/forums/index.php/t/1080353/) with author of ldt.   

# to apply this patch
modify internalmodelbuilder.mlua in eclipse folder, you may need [everything](http://www.voidtools.com/) to search files.
apply [this patch](https://github.com/ps5mh/ldt-self-autocomplete/commit/be1966456469a94e6e72b941f3c7417a40468130)

# to make this work, you should also aware
- add these line on top of your lua file
```lua
---
-- @module YOUR_LUA_MODULE_NAME
```
- make sure YOUR_LUA_MODULE_NAME matches your function parent table