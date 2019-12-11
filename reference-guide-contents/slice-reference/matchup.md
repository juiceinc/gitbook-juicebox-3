---
description: >-
  A Matchup slice is used to present the user with a view of the data separated
  compared against the average of those results with the highest positive and
  separate differences displayed.
---

# Matchup

## Matchup config

Matchup slices support the [common configuration options for all slices](../slices/slices-and-common-configuration.md). Additional options are:

{% tabs %}
{% tab title="Matchup Config Example" %}
```yaml
config:
  scoreTitleTemplate:"<%= selection(\"lollipop\", {\"dimension\":
    \"metric\"}) %> score"
  averageTitle: "Company average"
  differenceThreshold: 2
  displayModes: ["summary", "all"]
  showCount: false
  relatedItemsTitle: "Related courses"
  disableSort: true
```
{% endtab %}
{% endtabs %}

| Key | Optional | Values | Description |
| :--- | :--- | :--- | :--- |
| scoreTitleTemplate | Yes, default is "score" | Underscore.js template or plain text | The template that will be evaluated to determine the score title. |
| averageTitle | Yes, default is "industry average" | String | The text that indicated `average`. |
| differenceThreshold | Yes, default is 1 | Integer | The statistical difference to group the values by. Values within this threshold are considered to be “similar”. |
| displayModes | Yes, default is \[“summary”, “all”\] | Array of strings/mode names | Togglable display modes \(eg. show summary\|all\) |
| showCount | Yes, default is true | Boolean | Flag that indicates whether the count within the group should be shown |
| relatedItemsTitle | Yes, default is empty string | String | Each bar in matchup can have a list of related items. It is a list of strings displayed when a bar is hovered/selected. The title name of this list is defined here. |
| disableSort | Yes, default is false | Boolean | A boolean that controls if the data should be sorted. If set to `true`, sorting will be disabled and `displayModes` will be automatically set to `["all"]` |



## Flavors for Matchup

### Default \(matchup\)

The first dimension in self.dimensions is the grouping dimension, and the first metric is the value metric.

The code for the default matchup flavor looks as follows:

{% tabs %}
{% tab title="matchup\_data\_service.py" %}
```python
class MatchupV3Service(CensusService):
    def build_response(self):
        self.metrics = ('popdiff', )
        self.dimensions = ('state',)

        recipe = self.recipe().metrics(*self.metrics).dimensions(
            *self.dimensions)

        self.response['responses'].append(recipe.render())
```
{% endtab %}

{% tab title="stack.yaml" %}
```yaml
- slice_type: "matchup"
  slug: "matchup"
  title: "matchup"
  data_service: "matchup_data_service.MatchupV3Service"
  config:
    "differenceThreshold": 0.01
    "scoreTitleTemplate": "Population Change"
    "averageTitle": "Average Change"
```
{% endtab %}
{% endtabs %}

Any additional dimensions and metrics are not included in the output in any way.

