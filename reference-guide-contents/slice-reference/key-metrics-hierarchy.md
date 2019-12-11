---
description: >-
  A series of ranked nodes. Arrows can show flow. Some nodes include multiple
  pieces of data in it. The metrics in each node of the tree are comprised of
  the metrics that point to it.
---

# Key Metrics Hierarchy \(done\)

This slice is sometimes called the “squid” slice.

## Key Metrics Hierarchy config

Key Metrics Hierarchy slices support the [common configuration options for all slices](../slices/slices-and-common-configuration.md). Additional options are:

{% tabs %}
{% tab title="KMH config example" %}
```yaml
config:
  height: 500
  width: 960
  margin: {top: 60, right: 20, bottom: 20, left: 60}
  orient: bottom-to-top
  radius: 40
  groupLeafNodes: false
```
{% endtab %}
{% endtabs %}

| Key | Optional | Values | Description |
| :--- | :--- | :--- | :--- |
| height | Yes, defaults to 420 | Integer | The height of the visual component in pixels. |
| width | Yes, defaults to 800 | Integer | The width of the visual component in pixels. |
| margin | Yes, defaults to `{top: 40, right: 10, bottom: 10, left: 40}` | JS Object with "top", "bottom", "left", and "right" properties | The margins of the visual component in pixels. |
| orient | Yes, default is "top-to-bottom" | “top-to-bottom” or “bottom-to-top” or “left-to-right” or “right-to-left” | The orientation of the hierarchy. |
| radius | Yes, default is 25 | Integer | The radius of the nodes. |
| groupLeafNodes | Yes, default is true | Boolean | A flag that indicates if the leaf nodes should be grouped. |



