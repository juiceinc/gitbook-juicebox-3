---
description: >-
  A Nine Box slice is used to present the user with a view of the data plotted
  into sections of a grid along two axes. It currently only has a default
  flavor.
---

# Nine Box \(done\)

## Nine box config

Nine box slices support the [common configuration options for all slices](../slices/slices-and-common-configuration.md). Additional options are:

{% tabs %}
{% tab title="Nine Box Config Example" %}
```yaml
config:
  axisLabels:
    labels: ["Low", "My X axis", "High"]
    labels: ["Low", "My Y axis", "High"]
  boxLabels:
    position: ne
    row: 0,
    col: 2,
    text: "High traffic, Many bad stops"
  h_lines: ["50%", "25%"]
  height: 400
  invertXAxis: true
  invertYAxis: true
  margins:
    left: 50
    bottom: 40
    top: 20
    right: 20
  showBoundaryLabels: false
  sizeMinMax: [5, 10]
  tooltipTemplateName: #nine-box-custom-tooltip-template
  v_lines: ["50%", "25%"]
  width: 810
  x_bounds: [0,10]
  y_bounds: [0,10]
  searchFields: ["label", "score"]
```
{% endtab %}
{% endtabs %}

| Key | Optional | Values | Description |
| :--- | :--- | :--- | :--- |
| axisLabels | Yes | An array of {labels: \[\]} objects. the first object refers to X axis, the second object refers to Y axis | Name of the X and Y label |
| boxLabels | Yes | An array of {position \(n\|ne\|e\|se\|s\|sw\|w\|nw\),row,col,text} objects | An array of labels that should be displayed inside the box/regions. You can set the position the label should be displayed in the box |
| h\_lines | Yes, default is \[“33.3333%”, “33.3333%”\] | Array of widths between boundaries \(eg. \[“33.3333%”, “33.3333%”\] will make three equally spaced regions: 0%-33%, 33%-66%, 66%-100% of the width\) | Horizontal line boundaries |
| height | Yes, default is 500 | Integer | The height of the visual component in pixels |
| invertXAxis | Yes, default is `false` | Boolean | Should the X axis be inverted? eg. if \[0-100\] is inverted, 100 will appear asthe leftmost point and 0 will be the rightmost |
| invertYAxis | Yes, default is `false` | Boolean | Should the Y axis be inverted? eg. if \[0-100\] is inverted, 100 will appear at the bottom and 0 will be the topmost point |
| margins | Yes, default is {left: 40, bottom: 30, top: 10, right: 10} | {left, right, top, bottom}  | Margins of the visual component in pixels |
| showBoundaryLabels | Yes, default is set to true | Boolean | Should the region boundary labels be shown? |
| sizeMinMax | Yes, default is \[10, 10\] \(all bubbles have radius of 10px\) | array, \[min, max\] in pixels | Min/max size of the bubble \(radius, in pixels\) |
| tooltipTemplateName | Yes, default is \#nine-box-tooltip-template | CSS selector | CSS selector of the tooltip template \(displayed when mouse is over the bubble\) |
| v\_lines | Yes, default is \[“33.3333%”, “33.3333%”\] | Array of heights between boundaries \(eg. \[“33.3333%”, “33.3333%”\] will make three equally spaced regions: 0%-33%, 33%-66%, 66%-100% of the height\) | Vertical line boundaries |
| width | Yes | Integer | Width of the visual component in pixels |
| x\_bounds | Yes, by default domain is dynamically derived from X field data | Array of \[min, max\] | Domain \(possible min/max\) values on X axis. Use it if your data does not reflect the full range of points you want to display on the chart \(eg. your data is within 5-20 range, when the chart should be show in 0-100\) |
| y\_bounds | Yes, by default domain is dynamically derived from Y field data | Array of \[min, max\] | Domain \(possible min/max\) values on Y axis. Use it if your data does not reflect the full range of points you want to display on the chart \(eg. your data is within 5-20 range, when the chart should be show in 0-100\) |
| searchFields | Yes. Default is \[“label”\] | Array of \[min, max\] | The data attributes to be used for searching |

## Flavors of Nine Box

### Default \(nine box\)

Due to the requirements of the Nine box, there is not a default flavor presently.

### Quad Dimensions

The quad dimensions flavor uses the first dimension as the x value and the second dimension as the y value for grid placement. It renders a label based on the third dimension and the fourth dimension is used as the GUID. The first metric will be used as the size if present.

![](../../.gitbook/assets/ninebox-quaddim.png)

The code for the quad dimensions flavor looks as follows:

{% tabs %}
{% tab title="EIDataServices.py" %}
```python
class NineBoxService(EIService):

    def __init__(self, *args, **kwargs):
        super(NineBoxService, self).__init__(*args, **kwargs)
        self.automatic_filter_keys += ('category',)

    def build_response(self):
        self.dimensions = ['correlation', 'meanscore', 'question',
                           'question_order']

        recipe = self.recipe().metrics().dimensions(*self.dimensions
            ).filters(*self.filters)

    self.response['responses'].append(recipe.render('Ninebox'))
```
{% endtab %}

{% tab title="stack.yaml" %}
```yaml
- slice_type: "nine-box"
  slug: "nine-box"
  title: "Here are all the questions in <strong><%= lollipop.selectionDisplay() %></strong>. Select those you'd like to improve."
  config:
      "axisLabels":
      - "labels":
        - "Low"
        - "Performance"
        - "High"
      - "labels":
        - "Low"
        - "Potential"
        - "High"
      "height": 600
      "width": 900
      "margins":
        "top": 10
        "right": 10
        "bottom": 40
        "left": 100
      "pluralCountSuffix": "questions"
      "h_lines":
        - "33"
        - "34"
      "v_lines":
        - "33"
        - "34"
      "x_bounds":
        - 0
        - 1
      "y_bounds":
        - 2
        - 4
      "invertXAxis": True
      "tooltipTemplateName": "#nine-box-tooltip-ei-template"
      "boxLabels":
        -
          position: "ne"
          row: 0
          col: 2
          text: "High score but little impact on overall satisfaction"
        -
          position: "nw"
          row: 0
          col: 0
          text: "High score and impacts overall satisfaction"
        -
          position: "se"
          row: 2
          col: 2
          text: "Low score but little impact on overall satisfaction"
        -
          position: "sw"
          row: 2
          col: 0
          text: "Low score and impacts overall satisfaction"
  data_service: "EIDataServices.NineBoxService"
```
{% endtab %}

{% tab title="templates.html" %}
```markup
<script type="text/template" id="nine-box-tooltip-ei-template">
    <div class="nbox-tooltip-content--line1"><%= datum.label %></div>
    <table>
        <tr>
          <td style="text-align: left;"><%= (metadata.y && metadata.y.plural) || 'y' %>:</td>
          <td style="text-align: right; padding-left: 3px;"><%= datum.format('y', (metadata.y && metadata.y.format)) %></td>
        </tr>
        <tr>
          <td style="text-align: left;"><%= (metadata.x && metadata.x.plural) || 'x' %>:</td>
          <td style="text-align: right; padding-left: 3px;"><%= datum.format('x', (metadata.x && metadata.x.format)) %></td>
        </tr>
    </table>
</script>
```
{% endtab %}
{% endtabs %}

Any additional dimensions and metrics are not included in the output in anyway.

### Dual Metric

The dual metric flavor uses the first metric as the x value and the second metric as the y value for grid placement. It renders a label based on the first dimension. The third metric will be used as the size if present.

![](../../.gitbook/assets/ninebox-dualmetric.png)

The code for the dual metrics flavor looks as follows:

{% tabs %}
{% tab title="censusV2service.py" %}
```python
class NineBoxV3Service(CensusService):
    def build_response(self):
        self.metrics = ('popdiff', 'pctfemale')
        self.dimensions = ('state',)
        recipe = self.recipe().metrics(*self.metrics).dimensions(
            *self.dimensions).apply_global_filters(False)

        self.response['responses'].append(recipe.render())
```
{% endtab %}

{% tab title="stack.yaml" %}
```yaml
- slice_type: "nine-box"
  slug: "ninebox"
  title: "Nine Box"
  config:
    "axisLabels": [{"labels": ["Low", "Medium", "High"]}, {"labels": ["Slow", "Normal", "Fast"]}]
    "boxLabels":
    - "col": 2
      "position": "ne"
      "row": 0
      "text": "Small exposure, but high conversion rate"
  data_service: "censusv2service.NineBoxV3Service"
```
{% endtab %}
{% endtabs %}

Any additional dimensions and metrics are not included in the output in anyway.

