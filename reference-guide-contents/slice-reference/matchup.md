---
description: >-
  A Matchup slice is used to present the user with a view of the data separated
  compared against the average of those results with the highest positive and
  separate differences displayed.
---

# Matchup

## Matchup config

Matchup slices support the [common configuration options for all slices](../slices/slices-and-common-configuration.md). Additional options are:

### scoreTitleTemplate

The template that will be evaluated to determine the score title

| Optional: | Yes, default is “score” |
| :--- | :--- |
| Values: | Underscore.js template or plain text |
| Example: |  |

### averageTitle

The text that indicates `average`

| Optional: | Yes, default is “industry average” |
| :--- | :--- |
| Values: | String |
| Example: |  |

### differenceThreshold

The statistical difference to group the values by. Values within this threshold are considered to be “similar”.

| Optional: | Yes, default is 1 |
| :--- | :--- |
| Values: | number |
| Example: |  |

### displayModes

Togglable display modes \(eg. show summary\|all\)

| Optional: | Yes, default is \[“summary”, “all”\] |
| :--- | :--- |
| Values: | Array of strings/mode names |
| Example: |  |

### showCount \(matchup\)

Flag that indicates whether the count within the group should be shown

| Optional: | Yes, default is `true` |
| :--- | :--- |
| Values: | true\|false |
| Example: |  |

### disableSort \(matchup\)

A boolean that controls if the data should be sorted. If set to `true`, sorting will be disabled and `displayModes` will be automatically set to `["all"]`

| Optional: | Yes, default is `false` |
| :--- | :--- |
| Values: | true\|false |
| Example: |  |

## Flavors for Matchup

### Default \(matchup\)

The first dimension in self.dimensions is the grouping dimension, and the first metric is the value metric.

The code for the default matchup flavor looks as follows:

```text
class MatchupV3Service(CensusService):
    def build_response(self):
        self.metrics = ('popdiff', )
        self.dimensions = ('state',)

        recipe = self.recipe().metrics(*self.metrics).dimensions(
            *self.dimensions)

        self.response['responses'].append(recipe.render())
```

The slice in stack.yaml:

```text
- slice_type: "matchup"
  slug: "matchup"
  title: "matchup"
  data_service: "censusv2service.MatchupV3Service"
  config:
    "differenceThreshold": 0.01
    "scoreTitleTemplate": "Population Change"
    "averageTitle": "Average Change"
```

Any additional dimensions and metrics are not included in the output in any way.

