# Object Oriented Programming

- Table in Lua is an object
- Can create functions with the `.` / `:` operator
    - requires function to operate on the receiver of the operation
    - function class.func(self, arg)
    - we can use the `:` operator to hide the self parameter


- each object has a prototype which is a regular object where first object looks up any operation that it does not know about
- create an object to be used exclusively as a prototype for other objects

`setmetatable(a, {__index = b})`
- a looks up in b for any operation that it does not have