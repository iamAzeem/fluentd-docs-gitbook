# `csv` Formatter Plugin

The `csv` formatter plugin outputs an event as CSV.

```
"value1"[delimiter]"value2"[delimiter]"value3"\n
```


## Parameters

-   [Common Parameters](/configuration/plugin-common-parameters.md)
-   [Format Section Configurations](/configuration/format-section.md)


### `fields`

| type            | default            | version |
|:----------------|:-------------------|:--------|
| array of string | required parameter | 0.14.0  |

Specifies the output fields.


### `delimiter` (String, Optional. defaults to ",")

| type   | default | version |
|:-------|:--------|:--------|
| string | ,       | 0.14.0  |

Delimiter for values.

Use `\t` or `TAB` to specify tab character.


### `force_quotes`

| type | default | version |
|:-----|:--------|:--------|
| bool | `true`  | 0.14.0  |

If `false`, value won't be framed by quotes.


### `add_newline`

| type | default | version |
|:-----|:--------|:--------|
| bool | `true`  | 0.14.12 |

Adds `\n` to the result.


## Example

With this configuration:

```
<format>
  @type csv
  fields host,method
</format>
```

The following input

```
tag:    app.event
time:   1362020400
record: {"host":"192.168.0.1","size":777,"method":"PUT"}
```

is formatted to:

```
"192.168.0.1","PUT"\n
```

With `force_quotes false`, the result is:

```
192.168.0.1,PUT\n
```


------------------------------------------------------------------------

If this article is incorrect or outdated, or omits critical information, please
[let us know](https://github.com/fluent/fluentd-docs-gitbook/issues?state=open).
[Fluentd](http://www.fluentd.org/) is an open-source project under [Cloud Native
Computing Foundation (CNCF)](https://cncf.io/). All components are available
under the Apache 2 License.
