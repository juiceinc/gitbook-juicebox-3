---
description: >-
  A Flower slice shows data divided into equal segments. How far the data in
  each segment extends from the center depends on the value it represents.
---

# Flower

## Flower config

Flower slices support the [Common configuration options for all slices](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/slices/common_configuration.html). Additional options are:

### zoom

Turn on/off the zooming of the flowers.

| Optional: | Yes, by default zoom is set to true. |
| :--- | :--- |
| Values: | Boolean |
| Example: |  |

### zoomFactor

If zoom is true, the flower and its labels will be scaled by zoomFactor. For example, a zoomFactor of 2 will make it twice as big.

| Optional: | Yes, default is 2 |
| :--- | :--- |
| Values: | Integer |
| Example: |  |

### min

Explicitly set the min value. To be used when the dataset’s min value is not a decimal/percent falling within a range of 0 to 1.

| Optional: | Yes, default is 0 |
| :--- | :--- |
| Values: | Integer |
| Example: |  |

### max

Explicitly set the max value. To be used when the dataset’s max value is not a decimal/percent falling within a range of 0 to 1. When the max value is less than the dataset’s max value, the petal size will overflow the grey petal background.

| Optional: | Yes, default is 1 |
| :--- | :--- |
| Values: | Integer |
| Example: |  |

### useNodeSize

If each of the flowers should have a fixed size, then set this to true, and set the size of the flower in radius.

| Optional: | Yes, default is false. |
| :--- | :--- |
| Values: | Boolean |
| Example: |  |

### radius \(flower\)

Changes the radius of the flower’s outer ring. When it’s not set, it uses the width and height of the visualization to determine the size of each flower.

| Optional: | Yes, but necessary if useNodeSize is set to true. There is no default value |
| :--- | :--- |
| Values: | Integer |
| Example: |  |

### innerRadius \(flower\)

Changes the radius of the inner background circle of the visualization.

| Optional: | Yes, default is 15 |
| :--- | :--- |
| Values: | Integer |
| Example: |  |

### arcPadding

Controls the distance/space between the flower petals.

| Optional: | Yes, default is 0.1 |
| :--- | :--- |
| Values: | Float \(within 0-1 range\) |
| Example: |  |

### detailsTemplateName

The name of the template that should be used to display the details for a petal when it is hovered.

| Optional: | Yes |
| :--- | :--- |
| Values: | CSS Selector |
| Example: |  |

### height

The height of the visualization in pixels.

| Optional: | Yes, defaults to 600 |
| :--- | :--- |
| Values: | Integer |
| Example: |  |

### width

The width of the visualization in pixels.

| Optional: | Yes, defaults to 910 |
| :--- | :--- |
| Values: | Integer |
| Example: |  |

### margin

The margin of the visualization in pixels.

| Optional: | Yes, defaults to `{top: 40, right: 10, bottom: 10, left: 40}` |
| :--- | :--- |
| Values: | Object with “top”, “bottom”, “left”, and “right” properties |
| Example: |  |

