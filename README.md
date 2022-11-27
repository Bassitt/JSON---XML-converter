# Examples

<b>Example 1:</b>

Input example

```
{
    "transaction": {
        "id": "6753322",
        "number": {
            "@region": "Russia",
            "#number": "8-900-000-000"
        },
        "empty1": null,
        "empty2": { },
        "empty3": "",
        "inner1": {
            "inner2": {
                "inner3": {
                    "key1": "value1",
                    "key2": "value2"
                }
            }
        },
        "inner4": {
            "@": 123,
            "#inner4": "value3"
        },
        "inner4.2": {
            "": 123,
            "#inner4.2": "value3"
        },
        "inner5": {
            "@attr1": 123.456,
            "#inner4": "value4"
        },
        "inner6": {
            "@attr2": 789.321,
            "#inner6": "value5"
        },
        "inner7": {
            "#inner7": "value6"
        },
        "inner8": {
            "@attr3": "value7"
        },
        "inner9": {
            "@attr4": "value8",
            "#inner9": "value9",
            "something": "value10"
        },
        "inner10": {
            "@attr5": null,
            "#inner10": null
        },
        "inner11": {
            "@": null,
            "#": null
        },
        "inner12": {
            "@somekey": "attrvalue",
            "#inner12": null,
            "somekey": "keyvalue",
            "inner12": "notnull"
        },
        "inner13": {
            "@invalid_attr": {
                "some_key": "some value"
            },
            "#inner13": {
                "key": "value"
            }
        },
        "": {
            "#": null,
            "secret": "this won't be converted"
        }
    },
    "meta": {
        "version": 0.01
    }
}
```
Output example
```
Element:
path = transaction

Element:
path = transaction, id
value = "6753322"

Element:
path = transaction, number
value = "8-900-000-000"
attributes:
region = "Russia"

Element:
path = transaction, empty1
value = null

Element:
path = transaction, empty2
value = ""

Element:
path = transaction, empty3
value = ""

Element:
path = transaction, inner1

Element:
path = transaction, inner1, inner2

Element:
path = transaction, inner1, inner2, inner3

Element:
path = transaction, inner1, inner2, inner3, key1
value = "value1"

Element:
path = transaction, inner1, inner2, inner3, key2
value = "value2"

Element:
path = transaction, inner4

Element:
path = transaction, inner4, inner4
value = "value3"

Element:
path = transaction, inner4.2

Element:
path = transaction, inner4.2, inner4.2
value = "value3"

Element:
path = transaction, inner5

Element:
path = transaction, inner5, attr1
value = "123.456"

Element:
path = transaction, inner5, inner4
value = "value4"

Element:
path = transaction, inner6
value = "value5"
attributes:
attr2 = "789.321"

Element:
path = transaction, inner7
value = "value6"

Element:
path = transaction, inner8

Element:
path = transaction, inner8, attr3
value = "value7"

Element:
path = transaction, inner9

Element:
path = transaction, inner9, attr4
value = "value8"

Element:
path = transaction, inner9, inner9
value = "value9"

Element:
path = transaction, inner9, something
value = "value10"

Element:
path = transaction, inner10
value = null
attributes:
attr5 = ""

Element:
path = transaction, inner11
value = ""

Element:
path = transaction, inner12

Element:
path = transaction, inner12, somekey
value = "keyvalue"

Element:
path = transaction, inner12, inner12
value = "notnull"

Element:
path = transaction, inner13

Element:
path = transaction, inner13, invalid_attr

Element:
path = transaction, inner13, invalid_attr, some_key
value = "some value"

Element:
path = transaction, inner13, inner13

Element:
path = transaction, inner13, inner13, key
value = "value"

Element:
path = meta

Element:
path = meta, version
value = "0.01"
```
<b>Example 2:</b>

Input example

```
{
    "root1": {
        "@attr1": "val1",
        "@attr2": "val2",
        "#root1": {
            "elem1": {
                "@attr3": "val3",
                "@attr4": "val4",
                "#elem1": "Value1"
            },
            "elem2": {
                "@attr5": "val5",
                "@attr6": "val6",
                "#elem2": "Value2"
            }
        }
    },
    "root2": {
        "@attr1": null,
        "@attr2": "",
        "#root2": null
    },
    "root3": {
        "@attr1": "val2",
        "@attr2": "val1",
        "#root3": ""
    },
    "root4": "Value4"
}

```
Output example
```
Element:
path = root1
attributes:
attr1 = "val1"
attr2 = "val2"

Element:
path = root1, elem1
value = "Value1"
attributes:
attr3 = "val3"
attr4 = "val4"

Element:
path = root1, elem2
value = "Value2"
attributes:
attr5 = "val5"
attr6 = "val6"

Element:
path = root2
value = null
attributes:
attr1 = ""
attr2 = ""

Element:
path = root3
value = ""
attributes:
attr1 = "val2"
attr2 = "val1"

Element:
path = root4
value = "Value4"
```
<b>Example 3:</b>

Input example

```
{"root1":{"@attr1":"val1","@attr2":"val2","#root1":{"elem1":{"@attr3":"val3","@attr4":"val4","#elem1":"Value1"},"elem2":{"@attr5":"val5","@attr6":"val6","#elem2":"Value2"}}},"root2":{"@attr1":null,"@attr2":"","#root2":null},"root3":{"@attr1":"val2","@attr2":"val1","#root3":""},"root4":"Value4"}
```
Output example
```
Element:
path = root1
attributes:
attr1 = "val1"
attr2 = "val2"

Element:
path = root1, elem1
value = "Value1"
attributes:
attr3 = "val3"
attr4 = "val4"

Element:
path = root1, elem2
value = "Value2"
attributes:
attr5 = "val5"
attr6 = "val6"

Element:
path = root2
value = null
attributes:
attr1 = ""
attr2 = ""

Element:
path = root3
value = ""
attributes:
attr1 = "val2"
attr2 = "val1"

Element:
path = root4
value = "Value4"
```
