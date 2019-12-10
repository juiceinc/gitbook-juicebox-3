# Custom Slices \(sort of done. would love to develop this more. i just don't know enough.\)

A custom slice allows you to create a slice using any [d3 code.](https://d3js.org/)

## Custom Config

Custom slices support the [common configuration options for all slices](slices-and-common-configuration.md). Additional options are: None right now.

## Plugin

The plugin code must be wrapped in a `function(){}` that provides a namespace and returns a “chart”. This “chart” object must provide an interface for allowing the view to give it the current list of selections and for updating the visual appearance of the selected items.

{% tabs %}
{% tab title="Plugin Code" %}
```javascript
// Manage our own namespace to avoid polluting the global
// one.
function module() {

  // Object to be Returned
  // ---------------------

  // Create a closure to manage the public attributes
  // and methods we want to expose. This function (which
  // will be the the return value for our component) is
  // the main function that callers will use to create a chart.
  function chart(container, data, selectionChangedCallback) {
  }


  // Chart getter and setters
  // ------------------------

  chart.currentSelections = function(_a) {
    if (!arguments.length) return currentSelections;
    currentSelections = _a;
    return chart;
  };


  // Selections
  // -----------

  // Update the state of the selected items in the UI.
  chart.updateSelections = function() {
    // Update the appearance of the currently selected items stored in `currentSelections`.
  };

  // Return the public attributes and methods.
  return chart;
}
```
{% endtab %}
{% endtabs %}

The `chart` object will receive 3 arguments:

* The DOM container that will hold the visualization
* The data
* A callback to call when it needs to perform any selection.

{% tabs %}
{% tab title="Container, Data, and Callback" %}
```text
function chart(container, data, selectionChangedCallback) {}
```
{% endtab %}
{% endtabs %}

The plugin will never update any selection attribute of any data item. When it needs to perform a selection, it will use the callback provided to it and pass it a list of items whose selections will be toggled.

