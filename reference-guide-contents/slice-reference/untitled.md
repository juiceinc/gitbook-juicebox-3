---
description: >-
  A Flower slice shows data divided into equal segments. How far the data in
  each segment extends from the center depends on the value it represents.
---

# Flower \(done\)

## Flower config

Flower slices support the [Common configuration options for all slices](../slices/slices-and-common-configuration.md). Additional options are:

```text
config:
  zoom: false
  zoomFactor: 5
  min: 1
  max: 5
  useNodeSize: true
  radius: 100
  innerRadius: 10
  arcPadding: 0.5
  detailsTemplateName: "#my-flower-slice-details-template"
  height: 700
  width: 800
  margin:
    top: 10
    right: 0
    left: 0
    bottom: 10
```

| Key | Optional | Values | Description |
| :--- | :--- | :--- | :--- |
| zoom | Yes, by default, zoom is true | Boolean | Turn on/off the zooming of the flowers. |
| zoomFactor | Yes, default is 2 | Integer | If zoom is true, the flower and its labels will be scaled by zoomFactor. For example, a zoomFactor of 2 will make it twice as big. |
| min | Yes, default is 0 | Integer | Explicitly set the min value. To be used when the dataset’s min value is not a decimal/percent falling within a range of 0 to 1. |
| max | Yes, default is 1 | Integer | Explicitly set the max value. To be used when the dataset’s max value is not a decimal/percent falling within a range of 0 to 1. When the max value is less than the dataset’s max value, the petal size will overflow the grey petal background. |
| useNodeSize | Yes, default is false | Boolean | If each of the flowers should have a fixed size, then set this to true, and set the size of the flower in radius. |
| radius \(flower\) | Yes, but necessary if useNodeSize is set to true. | Integer | Changes the radius of the flower’s outer ring. When it’s not set, it uses the width and height of the visualization to determine the size of each flower. |
| innerRadius \(flower\) | Yes, default is 15 | Integer | Changes the radius of the inner background circle of the visualization. |
| arcPadding | Yes, default is 0.1 | Float \(within 0-1 range\) | Controls the distance/space between the flower petals. |
| detailsTemplateName | Yes | CSS Selector | The name of the template that should be used to display the details for a petal when it is hovered. |
| height | Yes, default is 600 | Integer | The height of the visualization in pixels. |
| width | Yes, default is 910 | Integer | The width of the visualization in pixels. |
| margin | Yes, defaults to `{top: 40, right: 10, bottom: 10, left: 40}` | Object with “top”, “bottom”, “left”, and “right” properties | The margin of the visualization in pixels. |



