# Tables
- Acts like a dictionary

## Declaration
- `table = {}`
- `table["x"] = 10`
- `table[1] = 2`

## Indicing

- `table[key]`
- `table.key -> table["key"]`

- __Important note__
    ```
    x = "y"
    a[x] = 10                 -- put 10 in field "y"
    print(a[x])   --> 10      -- value of field "y"
    print(a.x)    --> nil     -- value of field "x" (undefined)
    print(a.y)    --> 10      -- value of field "y"
    ```
    a.x -> a["x"] , but a[x] is equivalent to a["y"], therefore a.x is nil
    
## Iterating
    for index, value in ipairs() do 
        <code>
    end
    for index, value in pairs() do 
        <code>
    end

### ipairs() vs pairs()
- Ipairs iterates trhough table in numeric order
    - stops at first nil value
- Piars iterates through all the keys in unspecified order
    - includes non-numeri keys
    - use for associatvie arrays / tables with gaps
