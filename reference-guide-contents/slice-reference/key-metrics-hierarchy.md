# Key Metrics Hierarchy

A Key Metrics Hierarchy slice consists of a series of ranked nodes. Arrows can emanate to or from nodes to show the direction of flow. Some nodes include multiple pieces of data in it. The metrics in each node of the tree are comprised of the metrics that point to it.

This slice is sometimes called the “squid” slice.

## Key Metrics Hierarchy config

Key Metrics Hierarchy slices support the [common configuration options for all slices](../slices/slices-and-common-configuration.md). Additional options are:

### height \(kmh\)

The height of the visual component.

| Optional: | Yes, defaults to 420. |
| :--- | :--- |
| Values: | numbers \(in pixels\) |
| Example: |  |

### width \(kmh\)

The width of the visual component.

| Optional: | Yes, defaults to 800 |
| :--- | :--- |
| Values: | numbers \(in pixels\) |
| Example: |  |

### margin \(kmh\)

The margins of the visual component.

| Optional: | Yes, defaults to `{top: 40, right: 10, bottom: 10, left: 40}` |
| :--- | :--- |
| Values: | JS object with “top”, “bottom”, “left” and “right” properties |
| Example: |  |

### orient

Orientation of the hierarchy.

| Optional: | Yes, default is “top-to-bottom” |
| :--- | :--- |
| Values: | “top-to-bottom” or “bottom-to-top” or “left-to-right” or “right-to-left” |
| Example: |  |

### radius

The radius of the nodes.

| Optional: | Yes, default is 25. |
| :--- | :--- |
| Values: | number \(in pixels\) |
| Example: |  |

### groupLeafNodes

A flag that indicates if the leaf nodes should be grouped.

| Optional: | Yes, default is `true`. |
| :--- | :--- |
| Values: | true\|false |
| Example: |  |

