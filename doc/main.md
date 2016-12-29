Main module table
=================

```Lua
local mongo = require 'mongo'
```


Functions
---------

### mongo.type(value)
Returns the type name of `value`.

```Lua
print(mongo.type(mongo.Int32(123)))
print(mongo.type(mongo.Null))
```
Output:
```
mongo.Int32
mongo.Null
```


Constructors
------------

### mongo.Binary(data, [subtype])
Returns an instance of [BSON Binary][BSON type].

### mongo.BSON(value)
Returns an instance of [BSON document] cast from `value` that may take one of the following forms:
- a [BSON document] in which case this method does nothing;
- a JSON string;
- a table;
- a table/userdata with a `__tobson` metamethod that returns a table or a [BSON document]. This
  metamethod will also be called for nested values.

### mongo.Client(uri)
Returns a [Client] object. See also [MongoDB Connection String URI Format] for information on `uri`.

### mongo.DateTime(milliseconds)
Returns an instance of [BSON DateTime][BSON type].

### mongo.Double(number)
Returns an instance of [BSON Double][BSON type]. This type can be used to override automatic number
conversion where needed.

### mongo.Int32(integer)
Returns an instance of [BSON Int32][BSON type]. This type can be used to override automatic number
conversion where needed.

### mongo.Int64(integer)
Returns an instance of [BSON Int64][BSON type]. This type can be used to override automatic number
conversion where needed.

### mongo.Javascript(code, [scope])
Returns an instance of [BSON Javascript][BSON type].

### mongo.ObjectID([value])
Returns an instance of [BSON ObjectID]. If hexadecimal string `value` is provided, it is used
to initialize the instance. Otherwise, a new unique value is generated.

### mongo.Regex(regex, [options])
Returns an instance of [BSON Regex][BSON type].

### mongo.Timestamp(timestamp, increment)
Returns an instance of [BSON Timestamp][BSON type].


Singletons
----------

### mongo.MaxKey
The [BSON MaxKey][BSON type] singleton object.

### mongo.MinKey
The [BSON MinKey][BSON type] singleton object.

### mongo.Null
The [BSON Null][BSON type] singleton object.


[BSON document]: bson.md
[BSON ObjectID]: objectid.md
[BSON type]: bsontype.md
[Client]: client.md
[MongoDB Connection String URI Format]: https://docs.mongodb.com/manual/reference/connection-string/