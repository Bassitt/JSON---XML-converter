# Examples

<b>Example 1:</b>

Input example

```
{
    "transactions": {
        "id": "6753322",
        "data": [
            123,
            true,
            false,
            [ ],
            [],
            { },
            {},
            [
                1, 2, 3,
                {
                    "@attr": "value6",
                    "#element": "value7"
                }
            ],
            null,
            "",
            {
                "key1": "value1",
                "key2": {
                    "@attr": "value2",
                    "#key2": "value3"
                }
            },
            {
                "@attr2": "value4",
                "#element": "value5"
            }
        ]
    }
}
```
Output example
```
<transactions>
    <id>6753322</id>
    <data>
        <element>123</element>
        <element>true</element>
        <element>false</element>
        <element></element>
        <element></element>
        <element></element>
        <element></element>
        <element>
            <element>1</element>
            <element>2</element>
            <element>3</element>
            <element attr="value6">value7</element>
        </element>
        <element />
        <element></element>
        <element>
            <key1>value1</key1>
            <key2 attr="value2">value3</key2>
        </element>
        <element attr2="value4">value5</element>
    </data>
</transactions>
```
<b>Example 2:</b>

Input example

```
<?xml version = "1.0" encoding = "utf-8"?>
<transactions>
    <transaction>
        <id>6753322</id>
        <number region = "Russia">8-900-000-00-00</number>
        <date day = "12" month = "12" year = "2018"/>
        <amount currency="EUR">1000.00</amount>
        <completed>true</completed>
    </transaction>
    <transaction>
        <id>67533244</id>
        <number region = "Russia">8-900-000-00-01</number>
        <date day = "13" month = "12" year = "2018"/>
        <amount currency ="RUB">2000.00</amount>
        <completed>true</completed>
    </transaction>
    <transaction>
        <id>67533257</id>
        <number region="Russia">8-900-000-00-02</number>
        <date day = "14" month = "12" year = "2018"/>
        <amount currency = "EUR">3000.00</amount>
        <completed>false</completed>
    </transaction>
    <transaction>
        <id>67533259</id>
        <number region = "Ukraine">8-900-000-00-03</number>
        <date day = "15" month = "12" year = "2018"/>
        <amount currency = "GRN">4000.00</amount>
        <completed>false</completed>
    </transaction>
    <transaction>
        <id>67533566</id>
        <number region = "Ukraine">8-900-000-00-04</number>
        <date day = "16" month = "12" year = "2018"/>
        <amount currency = "USD">5000.00</amount>
        <completed>false</completed>
    </transaction>
</transactions>
```
Output example
```
{
    "transactions" : [
        {
            "id" : "6753322",
            "number" : {
                "@region" : "Russia",
                "#number" : "8-900-000-00-00"
            },
            "date" : {
                "@day" : "12",
                "@month" : "12",
                "@year" : "2018",
                "#date" : null
            },
            "amount" : {
                "@currency" : "EUR",
                "#amount" : "1000.00"
            },
            "completed" : "true"
        },
        {
            "id" : "67533244",
            "number" : {
                "@region" : "Russia",
                "#number" : "8-900-000-00-01"
            },
            "date" : {
                "@day" : "13",
                "@month" : "12",
                "@year" : "2018",
                "#date" : null
            },
            "amount" : {
                "@currency" : "RUB",
                "#amount" : "2000.00"
            },
            "completed" : "true"
        },
        {
            "id" : "67533257",
            "number" : {
                "@region" : "Russia",
                "#number" : "8-900-000-00-02"
            },
            "date" : {
                "@day" : "14",
                "@month" : "12",
                "@year" : "2018",
                "#date" : null
            },
            "amount" : {
                "@currency" : "EUR",
                "#amount" : "3000.00"
            },
            "completed" : "false"
        },
        {
            "id" : "67533259",
            "number" : {
                "@region" : "Ukraine",
                "#number" : "8-900-000-00-03"
            },
            "date" : {
                "@day" : "15",
                "@month" : "12",
                "@year" : "2018",
                "#date" : null
            },
            "amount" : {
                "@currency" : "GRN",
                "#amount" : "4000.00"
            },
            "completed" : "false"
        },
        {
            "id" : "67533566",
            "number" : {
                "@region" : "Ukraine",
                "#number" : "8-900-000-00-04"
            },
            "date" : {
                "@day" : "16",
                "@month" : "12",
                "@year" : "2018",
                "#date" : null
            },
            "amount" : {
                "@currency" : "USD",
                "#amount" : "5000.00"
            },
            "completed" : "false"
        }
    ]
}
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
        "special1": false,
        "special2": true,
        "empty1": null,
        "empty2": { },
        "empty3": [ ],
        "empty4": {},
        "empty5": [],
        "empty6": {

        },
        "empty7": [

        ],
        "empty8": "",
        "array1": [
            null, null
        ],
        "array2": [
            [],
            true, false, null,
            123, 123.456,
            "",
            {
                "key1": "value1",
                "key2": {
                    "@attr": "value2",
                    "#key2": "value3"
                }
            },
            {
                "@attr2": "value4",
                "#element": "value5"
            }
            ,
            {
                "@attr3": "value4",
                "#elem": "value5"
            },
            {
                "#element": null
            },
            {
                "#element": {
                    "deep": {
                        "@deepattr": "deepvalue",
                        "#deep": [
                            1, 2, 3
                        ]
                    }
                }
            }
        ],
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
            "@attr11": "value11",
            "#inner11": {
                "inner12": {
                    "@attr12": "value12",
                    "#inner12": {
                        "inner13": {
                            "@attr13": "value13",
                            "#inner13": {
                                "inner14": "v14"
                            }
                        }
                    }
                }
            }
        },
        "inner15": {
            "@": null,
            "#": null
        },
        "inner16": {
            "@somekey": "attrvalue",
            "#inner16": null,
            "somekey": "keyvalue",
            "inner16": "notnull"
        },
        "crazyattr1": {
            "@attr1": 123,
            "#crazyattr1": "v15"
        },
        "crazyattr2": {
            "@attr1": 123.456,
            "#crazyattr2": "v16"
        },
        "crazyattr3": {
            "@attr1": null,
            "#crazyattr3": "v17"
        },
        "crazyattr4": {
            "@attr1": true,
            "#crazyattr4": "v18"
        },
        "crazyattr5": {
            "@attr1": false,
            "#crazyattr5": "v19"
        },
        "crazyattr6": {
            "@attr1": "",
            "#crazyattr6": "v20"
        },
        "crazyattr7": {
            "@attr1": {},
            "#crazyattr7": "v21"
        },
        "crazyattr9": {
            "@attr1": {
                "@": 1,
                "#": 2,
                "": 3,
                "key": 4
            },
            "#crazyattr9": "v23"
        },
        "crazyattr10": {
            "@attr1": [],
            "#crazyattr10": "v24"
        },
        "crazyattr11": {
            "attr1": "better",
            "@attr1": {
                "key9": "value9"
            },
            "#crazyattr11": "v25"
        },
        "crazyattr12": {
            "@attr1": [
                ""
            ],
            "#crazyattr12": "v26"
        },
        "": {
            "#": null,
            "secret": "won't be converted"
        },
        "@": 123,
        "#": [
            1, 2, 3
        ]
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
        <special1>false</special1>
        <special2>true</special2>
        <empty1 />
        <empty2></empty2>
        <empty3></empty3>
        <empty4></empty4>
        <empty5></empty5>
        <empty6></empty6>
        <empty7></empty7>
        <empty8></empty8>
        <array1>
            <element />
            <element />
        </array1>
        <array2>
            <element></element>
            <element>true</element>
            <element>false</element>
            <element />
            <element>123</element>
            <element>123.456</element>
            <element></element>
            <element>
                <key1>value1</key1>
                <key2 attr="value2">value3</key2>
            </element>
            <element attr2="value4">value5</element>
            <element>
                <attr3>value4</attr3>
                <elem>value5</elem>
            </element>
            <element />
            <element>
                <deep deepattr="deepvalue">
                    <element>1</element>
                    <element>2</element>
                    <element>3</element>
                </deep>
            </element>
        </array2>
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
        <inner11 attr11="value11">
            <inner12 attr12="value12">
                <inner13 attr13="value13">
                    <inner14>v14</inner14>
                </inner13>
            </inner12>
        </inner11>
        <inner15></inner15>
        <inner16>
            <somekey>keyvalue</somekey>
            <inner16>notnull</inner16>
        </inner16>
        <crazyattr1 attr1="123">v15</crazyattr1>
        <crazyattr2 attr1="123.456">v16</crazyattr2>
        <crazyattr3 attr1="">v17</crazyattr3>
        <crazyattr4 attr1="true">v18</crazyattr4>
        <crazyattr5 attr1="false">v19</crazyattr5>
        <crazyattr6 attr1="">v20</crazyattr6>
        <crazyattr7 attr1="">v21</crazyattr7>
        <crazyattr9>
            <attr1>
                <key>4</key>
            </attr1>
            <crazyattr9>v23</crazyattr9>
        </crazyattr9>
        <crazyattr10 attr1="">v24</crazyattr10>
        <crazyattr11>
            <attr1>better</attr1>
            <crazyattr11>v25</crazyattr11>
        </crazyattr11>
        <crazyattr12>
            <attr1>
                <element></element>
            </attr1>
            <crazyattr12>v26</crazyattr12>
        </crazyattr12>
    </transaction>
    <meta>
        <version>0.01</version>
    </meta>
</root>
```
