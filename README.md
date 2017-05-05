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
Replace internalmodelbuilder.mlua in eclipse folder, with the one in this repo, you may need [everything](http://www.voidtools.com/) to search files.   
You may diff the two files to find the main idea of this patch.  

