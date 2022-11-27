# Examples

The greater-than symbol followed by a space (> ) represents the user input. Note that it's not part of the input.

<b>Example 1:</b>

Sample input

```
> <employee department = "manager">Garry Smith</employee>

```
Sample output
```
{
    "employee" : {
        "@department" : "manager",
        "#employee" : "Garry Smith"
    }
}

```
<b>Example 2:</b>

Sample input

```
> <person rate = "1" name = "Torvalds" />

```
Sample output
```
{
    "person" : {
        "@rate" : "1",
        "@name" : "Torvalds",
        "#person" : null
    }
}

```
<b>Example 3:</b>

Sample input

```
{
    "employee" : {
        "@department" : "manager",
        "#employee" : "Garry Smith"
    }
}

```
Sample output
```
<employee department = "manager">Garry Smith</employee>

```

<b>Example 4:</b>

Sample input

```
{
    "person" : {
        "@rate" : 1,
        "@name" : "Torvalds",
        "#person" : null
    }
}

```
Sample output
```
<person rate = "1" name = "Torvalds" />

```

<b>Example 5:</b>

Sample input

```
<host>127.0.0.1</host>

```
Sample output
```
{"host":"127.0.0.1"}

```

<b>Example 6:</b>

Sample input

```
{"jdk" : "1.8.9"}

```
Sample output
```
<jdk>1.8.9</jdk>

```