# Tours \(done\)

## Enabling stack tours

For tours to be displayed, [has\_tour](../reference-guide-contents/stack.yaml/#has_tour) needs to be `true` in the [stack.yaml](../reference-guide-contents/stack.yaml/).

## Building stack tours

Tours are defined in yaml files in a stack’s `help/` directory. These tours get loaded and displayed for a stack on the top of the stack page.

A Tour yaml file holds a definition for a Hopscotch tour. Hopscotch is a framework created by LinkedIn to help create tours \([http://linkedin.github](http://linkedin.github/) .io/hopscotch/\).

{% tabs %}
{% tab title="help/tour.yaml" %}
```text
id: "stack-ranked-list-2-guide-me"
name: "Welcome to the new Ranked List slice"
updated: 2017-10-31 17:34:47.702913+00:00
show_all_the_time: true
definition:
- "yOffset": 20
  "content": "Welcome to the new Ranked List slice!"
  "placement": "top"
  "target": ".slug-rl2"
  "title": "Ranked List Tour"
```
{% endtab %}
{% endtabs %}

| Key | Optional | Value | Description |
| :--- | :--- | :--- | :--- |
| id \(tours\) | No | &lt;= 70 character string. starts with 'stack-' | An unique id for a tour. All stack tour ids must start with the string ‘stack-‘. |
| name \(tours\) | No | &lt;= 200 character string | The name of the tour. This name will appear in the drop-down list of tours if the stack has more than one tour. |
| updated | No | Timestamp in YYY-MM-DD HH:MM:SS format | A timestamp for when the tour was updated. Set this to the current time when saving changes to the tour which would warrant a user seeing it again. |
| show\_all\_the\_time | Yes, default is true | true\|false | A flag that indicates if the tour should always show up in the drop down list of tours. If `false`, the tour will only appear when new or updated. |
| definition | No | A JSON definition of the tour. | The JSON definition for the Hopscotch tour. The most basic tour has the following definition: |

## Triggering tours from slices

Sometimes users want more explanation when they’re directly looking at a slice. We now provide a way to launch a specific tour from a slice.

This is provided by adding a link called “GUIDE ME” in the top-left corner of the slice \(next to where the legend shows up\). The link is enabled by providing the id of a tour as the `guide` for a slice.:

{% tabs %}
{% tab title="Enabling GUIDE ME" %}
```text
- slice_type: "free-form"
  slug: "overview"
  title: "Overview"
  guide: "stack-welcome-tour"
```
{% endtab %}
{% endtabs %}

The location of the link can be changed with the slice’s[ layout](../reference-guide-contents/slices/slices-and-common-configuration.md#layout) config option in [Common slice configuration](../reference-guide-contents/slices/slices-and-common-configuration.md).

{% tabs %}
{% tab title="GUIDE ME Location Change" %}
```text
- slice_type: "free-form"
  slug: "overview"
  title: "Overview"
  guide: "stack-welcome-tour"
  config:
    layout:
      "top-right": ["guide", "search"]
```
{% endtab %}
{% endtabs %}

The default label of the link \(“GUIDE ME”\) can also be changed with the `guideLabel` option:

{% tabs %}
{% tab title="guideLabel Change" %}
```text
- slice_type: "free-form"
  slug: "overview"
  title: "Overview"
  guide: "stack-welcome-tour"
  guideLabel: "Take a tour"
```
{% endtab %}
{% endtabs %}

