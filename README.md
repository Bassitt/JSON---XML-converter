# Examples

<b>Example 1:</b>

Input example

```
{
    "transaction": {
        "id": "6753322",
        "number": {
            "@region": "Russia",
            "#number": "8-900-000-00-00"
        },
        "amount": null
    }
}
```
Output example
```
<transaction>
    <id>6753322</id>
    <number region="Russia">8-900-000-00-00</number>
    <amount />
</transaction>```
<b>Example 2:</b>

Input example

```
{
    "transaction": {
        "id": "6753322",
        "number": {
            "@region": "Russia",
            "#number": "8-900-000-00-00"
        },
        "amount": null
    },
    "meta": {
        "version": 0.01
    }
}
```
Output example
```
<root>
    <transaction>
        <id>6753322</id>
        <number region="Russia">8-900-000-00-00</number>
        <amount />
    </transaction>
    <meta>
        <version>0.01</version>
    </meta>
</root>
```
<b>Example 3:</b>

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
<root>
    <transaction>
        <id>6753322</id>
        <number region="Russia">8-900-000-000</number>
        <empty1 />
        <empty2></empty2>
        <empty3></empty3>
        <inner1>
            <inner2>
                <inner3>
                    <key1>value1</key1>
                    <key2>value2</key2>
                </inner3>
            </inner2>
        </inner1>
        <inner4>
            <inner4>value3</inner4>
        </inner4>
        <inner5>
            <attr1>123.456</attr1>
            <inner4>value4</inner4>
        </inner5>
        <inner6 attr2="789.321">value5</inner6>
        <inner7>value6</inner7>
        <inner8>
            <attr3>value7</attr3>
        </inner8>
        <inner9>
            <attr4>value8</attr4>
            <inner9>value9</inner9>
            <something>value10</something>
        </inner9>
        <inner10 attr5="" />
        <inner11></inner11>
        <inner12>
            <somekey>keyvalue</somekey>
            <inner12>notnull</inner12>
        </inner12>
    </transaction>
    <meta>
        <version>0.01</version>
    </meta>
</root>
```
