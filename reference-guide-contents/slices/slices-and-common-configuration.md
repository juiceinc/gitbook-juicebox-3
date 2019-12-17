# Common Slice Configurations \(close to being done. waiting on chris' response a/b imports\)

## Common Slice Options: Example and Table

{% hint style="info" %}
The following configuration options can be applied to all slices.

Use the code block example as reference for the table.
{% endhint %}

{% tabs %}
{% tab title="Common Slice Example" %}
```text
slices:
- slice_type: card
  title: "What is the <%= lollipop.selectionDisplay() %> by <%= lollipop.metadata(lollipop.selectionType(), 'plural') %>?"
  subtitle: "My selection is <%= lollipop.selectionDisplay() %>"
  layout: twocolumns
  display_slice_as: default
  config:
    maxSelections: 1
    minSelections: 1
    noDataMessage: "Nothing to display"
    layout:
      top-left: []
    layoutFlags:
      "showLegend": true
    collapsable: false
    notifyOnDataSetChange: true
  data_service: services.CardService
  include_commands: 
  - download-data
  - download-image
```
{% endtab %}
{% endtabs %}

| Key | Optional | Type | Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| slice\_type | No | String | Any valid slice type | The type of slice to display |
| title | Yes | String | A valid Juicebox template | A dynamic title to display on the top or side of the slice. The title position depends on the `layout`. |
| subtitle | Yes | String | A valid Juicebox template | A dynamic subtitle to display. The subtitle position depends on the `layout`. |
| layout | Yes | String | [default](slices-and-common-configuration.md#layout-default), [bare](slices-and-common-configuration.md#layout-bare), [twocolumns](slices-and-common-configuration.md#layout-twocolumns), [twocolumns-twothirds](slices-and-common-configuration.md#layout-twocolumns-twothirds) | Layout changes the organization, sizing, and placement of slice components. [Check out a more detailed description of the values here](slices-and-common-configuration.md#layout). |
| display\_slice\_as | Yes | String | [default](slices-and-common-configuration.md#display_slice_as_details-default), [vis](slices-and-common-configuration.md#display_slice_as_details-viz),[ pil](slices-and-common-configuration.md#display_slice_as_details-pill) | Determines how the slice displays in relation to the pill.  [Check out descriptions of the values here.](slices-and-common-configuration.md#display_slice_as-details) |
| data\_service | Yes | String | A[ python data service](slices-and-common-configuration.md#python-data-services) reference _or_ a [json filename](slices-and-common-configuration.md#fixture-data-services) in the stack's fixtures directory | Provides data to the slice. While technically optional, free-form slices are the only slices that don't require a data service to function. [Check out a more detailed description of how to use a python data service and json filename here.](slices-and-common-configuration.md#data_service) |
| include\_commands | Yes | List\(of strings\) | Valid command names | What commands should be included on this slice. Commands allow users to perform actions using the data on the slice. [Learn more about custom and built-in commands here.](../../enhancements-contents/writing-custom-app-commands.md) |
| config | Yes | Object | valid Juicebox Key: Value combinations |  |
| **OPTIONS IN CONFIG** |  |  |  | The following options appear within the config object. |
| noSelectionTextTemplate | Yes | String | The name of the template to render | This allows slices to customize the text that displays in the pill when there are no selections. Only activated when `display_slice_as` is set to `pill` or `default .`  |
| minSelections | Yes \(Default is 0\) | Integer | Number | The minimum number of selections allowed in this slice. Any number bigger than 0 will disable `clear selections` option in the slice header \(local filters/slice selections\). |
| maxSelections | Yes | Integer | Number | The maximum number of selections allowed in this slice. |
| noDataMessage | Yes | String | Any text you want to display | A message to display when when no data is retrieved from the server. |
| layout | Yes | Object | JS Object with in this form: `{top-left: [], top-right: [], bottom-left: [], bottom-right: [], bottom-center: []}`, where each array is a list of widgets \(body\|notes\|commands\|controls\|legend\|search\) in that location on the page.  | An object that defines the layout of all widgets in the slice. Contains layout locations \(eg. top-left\) with widget names \(eg. controls\) in them. |
| layoutFlags | Yes | Object | An object with `show{WidgetName}` as property name and show/no-show flags as their values | Sets show/hide state for slice widgets \(search, etc…\). Find out more information about widget options here. |
| collapsable | Yes \(Default is true\) | Boolean | true\|false | A boolean flag that indicates if a slice is collapsable \(would expand/collapse when clicked on the header\). By default all slices are collapsable \(no need to define collapsed=true\). Useful when a slice needs to stay expanded no matter what \(collapsable = false\). |
| notifyOnDataSetChange | Yes \(Default is false\) | Boolean | true\|false | A boolean flag that indicates if a slice should notify all the slices below it \(that are listening to it\) when its data set changes so they can fetch their data. |

## layout details

As you saw on the table above, the layout can change the organization, sizing, and placement of slice components. We also saw the four possible values that you would use to cause these changes to take affect. The real question is, what do they each really mean? Let's take a look at it now.

### layout: default

`default`: This is the standard layout where the visualization content takes the full width of the slice. The slice `title` header is on top, with component locations above and below the vis

![layout: default](../../.gitbook/assets/image%20%282%29.png)

### layout: bare

`bare` removes all components except the visualization

![layout: bare](../../.gitbook/assets/image%20%283%29.png)

### layout: twocolumns

`twocolumns`: When using a two column layout, the slice `title`, discussions button, filter pill, and subtitle are all placed to the left of the visualization.

This layout is good when you would like to use more text to describe what the user is seeing.

![layout: twocolumns](../../.gitbook/assets/image%20%284%29.png)

The `subtitle` component is available in this layout, and sits below the `title` and above the filter pill.

{% hint style="info" %}
Depending on the slice type, the components may have different default layout locations to best support the reading and use of the visualization. Also, some slices may scroll horizontally to see the full visualization.
{% endhint %}

### layout: twocolumns-twothirds

`twocolumns-twothirds`: This two column variation makes the left side one third and the right visualization side into two thirds.

![layout: twocolumns-twothirds](../../.gitbook/assets/image%20%285%29.png)

## display\_slice\_as\_details

We know from the table above that `display_slice_as` determines how the slice displays in relation to the pill. We also know that there are three allowed values: `default`, `vis`, and `pill`. What we don't know yet is what they do. Let's take a look at that now. 

### display\_slice\_as\_details: default

`default` displays the slice in its default state - with its visualization and pill.

### display\_slice\_as\_details: viz

`viz` prevents the pill from showing up in the slice but still allows the pill to show up in the filter bar at the top of the story. 

### display\_slice\_as\_details: pill

`pill` hides the slice visualization from being displayed, and only shows the pill as if it were the entire slice. This behavior can be beneficial for having functionality similar to the `option-chooser` slice but with a more compact design. Unlike the pill’s standard behavior, this pill displays even when there is no selection made, substituting the selection for a summary of the slice’s options. 

## data\_service

Provides data to the slice. 

{% hint style="warning" %}
While data services are optional, a data service should be provided for all slices except for `free-form`slices.

If the slice doesn't have a data service, an empty response will be generated, and the `WithNoData` mixin will be applied.
{% endhint %}

### Python data services

Python data services are referenced by supplying a python filename and data service class name relative to the stack location.

{% tabs %}
{% tab title="Python Data Service Example" %}
```text
slices:
- slice_type: card
  data_service: services.CardService
```
{% endtab %}
{% endtabs %}

### Fixture data services

Alternately, a json file containing valid Juicebox response data located in the stack’s `fixtures/` directory. The json filename must end in `.json`. 

The fixture directory is relative to the stack location.  If a `fixtures/` directory is not present, create it.

{% tabs %}
{% tab title="Json Fixture Example" %}
```text
slices:
- slice_type: card
  data_service: card.json
```
{% endtab %}
{% endtabs %}

## config.layoutFlags

Need to know more about layoutFlags to see if it's necessary to bring some extra stuff over. I think it'll be necessary, but i'll ask chris when i get a response on the import stuff.

## Additional template options

Slice appearance can also be heavily customized with custom templates. See [Customizing slice templates](../../enhancements-contents/customizing-slice-templates.md)

