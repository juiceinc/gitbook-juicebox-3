---
description: >-
  A Leaderboard slice is used to present the user with a view of the one or more
  values grouped by a common dimension and sorted. It allows a quick view of the
  Top 10, Bottom 10 and Top and Bottom 5.
---

# Leaderboard

## Leaderboard config

Leaderboard slices support the [Common configuration options for all slices](../slices/slices-and-common-configuration.md). Additional options are:

### columns

An array of column descriptions \(in the order they need to be displayed in leaderboard\). Each cell in Leaderboard consists of a Name and a Value of \(eg. \[StudentX 99\] \[StudentZ 23\]\). The name field for each cell should be specified as the first item in columns array. The first column \(name field\) will not be rendered in leaderboard, its field value rather becomes the name part in each cell. Your first column is NOT an ID or a numeric value, it should be a property name in each data item that has a string value. Value fields should be specified next, in the order they need to appear in the leaderboard.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Optional:</th>
      <th style="text-align:left">Yes, but results might be unexpected (might pick the wrong name column)
        if columns not defined</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Values:</td>
      <td style="text-align:left">An array of <code>{name,searchable,reverse}</code> objects</td>
    </tr>
    <tr>
      <td style="text-align:left">Example:</td>
      <td style="text-align:left">
        <p>config:</p>
        <p>columns: [{&#x201C;name&#x201D;: &#x201C;student_name&#x201D;,&#x201D;searchable&#x201D;:
          false,&#x201D;reverse&#x201D;: false, &#x201C;format&#x201D;: &#x201C;&#x201D;},
          {&#x2026;}, &#x2026;]</p>
      </td>
    </tr>
  </tbody>
</table>### ignoreNulls

Should the `null` values be ignored?

| Optional: | Yes, defaults to `true` \(will be ignored\) |
| :--- | :--- |
| Values: | true\|false |
| Example: |  |

### showMode

Which records should leaderboard initially show? Top X? Bottom X? or Top X/2 and Bottom X/2?

| Optional: | Yes, defaults to `top` |
| :--- | :--- |
| Values: | top\|bottom\|both |
| Example: |  |

### numberOfRows

Number of rows displayed in leaderboard.

| Optional: | Yes, defaults to 10 |
| :--- | :--- |
| Values: | integer |
| Example: |  |

## Flavors of Leaderboard

### Default \(leaderboard\)

The default flavor renders a many metrics and dimensions grouped by a single dimension. The primary dimension is used as the grouping dimension.

![](../../.gitbook/assets/leaderboard-default.png)

The code for the default Trend flavor looks as follows for rendering multiple datasets:

```text
class LeaderboardV3Service(CensusService):
    def build_response(self):
        self.metrics = ('pop2000', 'pop2008', 'popdiff')
        self.dimensions = ('state', )
        recipe1 = self.recipe().metrics(*self.metrics).dimensions(
            *self.dimensions)
        self.dimensions = ('age', )
        recipe2 = self.recipe().metrics(*self.metrics).dimensions(
            *self.dimensions)

        results = RecipePool([
            (recipe1, 'States'), (recipe2, 'Ages'),
        ]).run()
        self.response['responses'] = results
```

And the slice in stack.yaml:

```text
- slice_type: "leaderboard"
  slug: "leaderboard"
  title: "Leaderboard"
  data_service: "someService.LeaderboardV3Service"
```

