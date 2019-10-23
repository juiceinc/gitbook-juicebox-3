# Common Slice Configurations

{% hint style="info" %}
The following configuration options can be applied to all slices
{% endhint %}

## slice\_type

The type of slice to display

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | Any valid slice type | None | No |

```yaml
slices:
- slice_type: card
  ...
```

## title

A dynamic title to display on the top or side of the slice. The title position depends on the `layout`.

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | A valid Juicebox template | "" \(an empty string\) | Yes |

```yaml
slices:
- slice_type: card
  title: "What is the <%= lollipop.selectionDisplay() %> by <%= lollipop.metadata(lollipop.selectionType(), 'plural') %>?"
  ...
```

## subtitle

A dynamic subtitle to display. The subtitle position depends on the `layout`.

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | A valid Juicebox template | "" \(an empty string\) | Yes |

```yaml
slices:
- slice_type: card
  subtitle: "My selection is <%= lollipop.selectionDisplay() %>"
  ...
```

## layout

Layout changes the organization, sizing, and placement of slice components

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | default, bare, twocolumns, twocolumns-twothirds | default | Yes |

```yaml
slices:
- slice_type: card
  layout: twocolumns
  ...
```

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

### layout: twocolumns-twothirds

`twocolumns-twothirds`: This two column variation makes the left side one third and the right visualization side into two thirds.

![layout: twocolumns-twothirds](../../.gitbook/assets/image%20%285%29.png)

## display\_slice\_as

Determines how the slice displays in relation to the pill. 

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | default, vis, pill | default | Yes |

`default` displays the slice in its default state - with its visualization and pill.

`viz` prevents the pill from showing up in the slice but still allows the pill to show up in the filter bar at the top of the story. 

`pill` hides the slice visualization from being displayed, and only shows the pill as if it were the entire slice. This behavior can be beneficial for having functionality similar to the `option-chooser` slice but with a more compact design. Unlike the pill’s standard behavior, this pill displays even when there is no selection made, substituting the selection for a summary of the slice’s options. 

## data\_service

Provides data to the slice. 

{% hint style="warning" %}
While data services are optional, a data service should be provided for all slices except for `free-form`slices.
{% endhint %}

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | A python data service reference _or_ a json filename in the stack's fixtures directory | null | Yes |

### Python data services

Python data services are referenced by supplying a python filename and data service class name relative to the stack location.

```text
slices:
- slice_type: card
  data_service: services.CardService
```

### Fixture data services

Alternately, a json file containing valid juicebox response data located in the stack’s `fixtures/` directory. The json filename must end in `.json`. 

The fixture directory is relative to the stack location.  If a `fixtures/` directory is not present, create it.

```text
slices:
- slice_type: card
  data_service: card.json
```

### Providing no data service

If the `data_service` property is missing for a slice, an empty response will be generated and the `WithNoData` **mixin** will be applied. `data_service` should only be omitted for free-form slices.

```text
slices:
- slice_type: card
  data_service: null
```

## include\_commands

What commands should be included on this slice. Commands allow users to perform actions using the data on the slice. 

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| list \(of strings\) | Valid command names | \[\] |  |

To create custom app commands and learn more about built-in commands, see [Writing app command](../../enhancements/writing-custom-app-commands.md)

```text
slices:
- slice_type: card
  include_commands: 
  - download-data
  - download-image
```

## config.noSelectionTextTemplate

This allows slices to customize the text that displays in the pill when there are no selections.

| Optional: | Yes, only activated when `display_slice_as` is set to `pill` or `default` |
| :--- | :--- |
| Values: | The name of the template to render |
| Example: |  |

## config.minSelections

The minimum number of selections allowed in this slice. Any number bigger than 0 will disable `clear selections` option in the slice header \(local filters/slice selections\).

| Optional: | yes, default is 0 |
| :--- | :--- |
| Values: | numbers |
| Example: |  |

## config.maxSelections

The maximum number of selections allowed in this slice.

| Optional: | yes |
| :--- | :--- |
| Values: | integer |
| Example: |  |

## config.noDataMessage

A message to display when when no data is retrieved from the server.

| Optional: | yes |
| :--- | :--- |
| Values: | text |
| Example: |  |

## config.layout

An object that defines the layout of all widgets in the slice. Contains layout locations \(eg. top-left\) with widget names \(eg. controls\) in them.

| Optional: | yes |
| :--- | :--- |
| Values: | JS Object with in this form: `{top-left: [], top-right: [], bottom-left: [], bottom-right: [], bottom-center: []}`, where each array is a list of widgets \(body\|notes\|commands\|controls\|legend\|search\) in that location on the page |
| Example: |  |

## config.layoutFlags

Sets show/hide state for slice widgets \(search, etc…\). Note: To show the legend widget, in addition to setting the `showLegend` flag to `true`, you also need to have a non-empty `legend` object inside `templateContext` in the response.

| Optional: | Yes, default is |
| :--- | :--- |
| Values: | An object with `show{WidgetName}` as property name and show/no-show flags as their values |
| Example: |  |

## config.collapsable

A boolean flag that indicates if a slice is collapsable \(would expand/collapse when clicked on the header\). By default all slices are collapsable \(no need to define collapsed=true\). Useful when a slice needs to stay expanded no matter what \(collapsable = false\).

| Optional: | yes, default is `true` |
| :--- | :--- |
| Values: | Boolean \(true \| false\) |
| Example: |  |

## config.notifyOnDataSetChange

A boolean flag that indicates if a slice should notify all the slices below it \(that are listening to it\) when its data set changes so they can fetch their data.

| Optional: | yes, default is `false` |
| :--- | :--- |
| Values: | Boolean \(true \| false\) |
| Example: |  |

## Additional template options

Slice appearance can also be heavily customized with custom templates. See [Customizing slice templates](../../enhancements/customizing-slice-templates.md)

