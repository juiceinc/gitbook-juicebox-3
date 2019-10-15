# Defining and Configuring Global Filters

## Defining Global Filters

In the `stack.yaml` file, there is a `global_filters_service` that needs to point to the data service class in our stack’s python module or a json file found in the fixtures directory.

For example to use the `FilterService` class found in the `basicservice.py` file:

```yaml
global_filters_service: "basicservice.FilterService"
```

## Global Filter Configurations and Options

Global filters are configured using `filters_config` in `stack.yaml`. Configuration looks like this:

```text
filters_config:
  global:
    defaultSort: "name"
  "audit_quarter":
    maxSelections: 1
  "facility":
    maxSelections: 1
```

The global filters can be configured on a per-stack basis. A special config key called `global` is used to specify configuration that is common across all the filters.

### Sorting Configurations

The sorting configs are not specific to any particular filter and are applied across all of them. The refreshing of the filters is also controlled by a single option available under “global” called “refresh”. Sometimes users may make filter selections that are inelligible or narrow down the data greatly, causing very little data to show in their slices. Enabling the “refresh” config avoids this scenario by filtering down to eligible remaining global filter options.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p></p>
        <p>Option</p>
      </th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>defaultSort</code>
      </td>
      <td style="text-align:left">Can either be &#x201C;name&#x201D; or &#x201C;count&#x201D;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>defaultSortDirection</code>
      </td>
      <td style="text-align:left">Use -1 for descending and 1 for ascending.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>disableSort</code>
      </td>
      <td style="text-align:left">true/false to turn off sorting. The default is sorting is enabled.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>refresh</code>
      </td>
      <td style="text-align:left">true/false to indicate if the filters should refresh themselves when selections
        change.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>filterLabel</code>
      </td>
      <td style="text-align:left">Can be any string to override labelling filters as &#x201C;Filters&#x201D;</td>
    </tr>
  </tbody>
</table>An example:

```text
filters_config:
  global:
    "defaultSort": "name"
    "defaultSortDirection": -1
    "disableSort": false
    "refresh": true
```

### Per-Filter Configurations

The following config properties can be specified on a per filter basis. Use the filter’s `group_by_type` property as the key.

| Option | Description |
| :--- | :--- |
| `minSelections` | The minimum number of selections required for this filter. This value will be used to automatically select those many items if they aren’t already. Defaults to 0. |
| `maxSelections` | The maximum number of selections allowed for this filter. Defaults to the maximum numeric value representable in JavaScript \(approximately 1.79E+308\). |
| `filterTemplateName` | A name of a template that would be used to render **all** the items in that filter. |

An example:

```text
{group_by_type}:
    minSelections: 0
    maxSelections: 1
    filterTemplateName: "#mooTemplate"
```

