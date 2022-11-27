# Examples

<b>Example 1:</b>

Input example

```
<transaction>
    <id>6753322</id>
    <number region="Russia">8-900-000-00-00</number>
    <nonattr />
    <nonattr></nonattr>
    <nonattr>text</nonattr>
    <attr id="1" />
    <attr id="2"></attr>
    <attr id="3">text</attr>
    <email>
        <to>to_example@gmail.com</to>
        <from>from_example@gmail.com</from>
        <subject>Project discussion</subject>
        <body font="Verdana">Body message</body>
        <date day="12" month="12" year="2018"/>
    </email>
</transaction>
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
value = "8-900-000-00-00"
attributes:
region = "Russia"

Element:
path = transaction, nonattr
value = null

Element:
path = transaction, nonattr
value = ""

Element:
path = transaction, nonattr
value = "text"

Element:
path = transaction, attr
value = null
attributes:
id = "1"

Element:
path = transaction, attr
value = ""
attributes:
id = "2"

Element:
path = transaction, attr
value = "text"
attributes:
id = "3"

Element:
path = transaction, email

Element:
path = transaction, email, to
value = "to_example@gmail.com"

Element:
path = transaction, email, from
value = "from_example@gmail.com"

Element:
path = transaction, email, subject
value = "Project discussion"

Element:
path = transaction, email, body
value = "Body message"
attributes:
font = "Verdana"

Element:
path = transaction, email, date
value = null
attributes:
day = "12"
month = "12"
year = "2018"
```
<b>Example 2:</b>

Input example

```
<node>
    <child name = "child_name1" type = "child_type1">
        <subchild id = "1" auth="auth1">Value1</subchild>
    </child>
    <child name = "child_name2" type = "child_type2">
        <subchild id = "2" auth="auth1">Value2</subchild>
        <subchild id = "3" auth="auth2">Value3</subchild>
        <subchild id = "4" auth="auth3"></subchild>
        <subchild id = "5" auth="auth3"/>
    </child>
</node>

```
Output example
```
Element:
path = node

Element:
path = node, child
attributes:
name = "child_name1"
type = "child_type1"

Element:
path = node, child, subchild
value = "Value1"
attributes:
id = "1"
auth = "auth1"

Element:
path = node, child
attributes:
name = "child_name2"
type = "child_type2"

Element:
path = node, child, subchild
value = "Value2"
attributes:
id = "2"
auth = "auth1"

Element:
path = node, child, subchild
value = "Value3"
attributes:
id = "3"
auth = "auth2"

Element:
path = node, child, subchild
value = ""
attributes:
id = "4"
auth = "auth3"

Element:
path = node, child, subchild
value = null
attributes:
id = "5"
auth = "auth3"

```
<b>Example 3:</b>

Input example

```
<node><child name="child_name1" type="child_type1"><subchild id="1" auth="auth1">Value1</subchild></child><child name="child_name2" type="child_type2"><subchild id="2" auth="auth1">Value2</subchild><subchild id="3" auth="auth2">Value3</subchild><subchild id="4" auth="auth3"></subchild><subchild id="5" auth="auth3"/></child></node>

```
Output example
```
Element:
path = node

Element:
path = node, child
attributes:
name = "child_name1"
type = "child_type1"

Element:
path = node, child, subchild
value = "Value1"
attributes:
id = "1"
auth = "auth1"

Element:
path = node, child
attributes:
name = "child_name2"
type = "child_type2"

Element:
path = node, child, subchild
value = "Value2"
attributes:
id = "2"
auth = "auth1"

Element:
path = node, child, subchild
value = "Value3"
attributes:
id = "3"
auth = "auth2"

Element:
path = node, child, subchild
value = ""
attributes:
id = "4"
auth = "auth3"

Element:
path = node, child, subchild
value = null
attributes:
id = "5"
auth = "auth3"
```
