# `hash` Formatter Plugin

The `hash` formatter plugin converts an event to Ruby hash.

By default, `hash` formatter result does not contain `tag` and `time` field.


## Parameters

-   [Common Parameters](/configuration/plugin-common-parameters.md)
-   [Format Section Configurations](/configuration/format-section.md)


### `add_newline`

| type | default | version |
|:-----|:--------|:--------|
| bool | true    | 0.14.12 |

Adds `\n` to the result.


## Example

```
tag:    app.event
time:   1362020400
record: {"host":"192.168.0.1","size":777,"method":"PUT"}
```

This incoming event is formatted to:

```
{"host"=>"192.168.0.1","size"=>777,"method"=>"PUT"}
```


------------------------------------------------------------------------

If this article is incorrect or outdated, or omits critical information, please
[let us know](https://github.com/fluent/fluentd-docs-gitbook/issues?state=open).
[Fluentd](http://www.fluentd.org/) is an open-source project under [Cloud Native
Computing Foundation (CNCF)](https://cncf.io/). All components are available
under the Apache 2 License.
