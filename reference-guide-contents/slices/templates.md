---
description: Templates turn data into html. Juicebox has many templates built-in.
---

# Templates

Juicebox uses Juice’s open-source [Dunderscore Templates](https://github.com/juiceinc/dunderscore) library. Dunderscore combines the flexibility of using plain javascript Underscore templates \(see [http://underscorejs.org/\#template](http://underscorejs.org/#template)\) with filters inspired by Vega Datalib \([https://github.com/vega/datalib/wiki/Formatting\#dl\_template](https://github.com/vega/datalib/wiki/Formatting#dl_template)\).

## Two types of templates

Templates have global access to all data in any slice by referring to other slugs. Some templates are bound to a data object called `datum`.

## Built-in template functions

All the built-in functions are called by referencing the slug for the slice you’re interested in followed by the function name.

```markup
<%= <slug>.<functionName>() %>
```

### selection

Provides the list of selected items in the slice with slug &lt;slug&gt;. Each item will have an `id`, a `label`, and a `group_by_type`.

```markup
optionchooser.selection()
// Returns: [{id: 'expenditures', 'label': 'Expenditures', 'group_by_type': 'sel_type'}]
```

### selectionDisplay

Provides a string of the selected items of the slice with slug &lt;slug&gt; for display.

* If there are no selections, displays “All &lt;dimension&gt;s”
* If there is 1 selection, displays “&lt;label\_of\_the\_selected\_item&gt;”
* If there are &gt; 1 selections, displays “&lt;num\_of\_selections&gt; &lt;dimension&gt;s”

This is a shortcut way of referring to the following template.

```markup
//ranked_list.selectionDisplay() is the same as

<% if (ranked_list.selection().length == 1) { %>
    <%= ranked_list.selection()[0].label %>
<% } else if (ranked_list.selection().length > 1) { %>
    <%= ranked_list.selection().length ranked_list.metadata(ranked_list.selectionType(), 'plural') %>
<% } else { %>
    All <%=ranked_list.metadata(ranked_list.selectionType(), 'plural')%>
<% } %>
```

This method also accepts a “dimension” parameter that limits the display string to only the selection of items whose `group_by_type` == “dimension”. This is helpful for slices like the Option Chooser that can show multiple groups of options, each with their own `group_by_type`.

```text
// option_chooser.selectionDisplay('attempt_type') is the same as

<%
  var selection = option_chooser.selection(),
      type      = 'attempt_type';

  selection = selection.filter(function(d) {
    return d.group_by_type == type;
  });
%>

<% if (selection.length == 1) { %>
    <%= selection[0].label %>
<% } else if (selection.length > 1) { %>
    <%= selection.length option_chooser.metadata(type, 'plural') %>
<% } else { %>
    All <%= option_chooser.metadata(type, 'plural')%>
<% } %>
```

### selectionListDisplay

Provides a comma separated list of the selected items of the slice with slug &lt;slug&gt; for display.

* If there are no selections, displays “All &lt;dimension&gt;s”
* If there is 1 selection, displays “&lt;label\_of\_the\_selected\_item&gt;”
* If there are &gt; 1 selections, displays “&lt;label\_of\_selection\_1&gt;, &lt;label\_of\_selection\_2&gt;”

This is a shortcut way of referring to the following template.

```text
//ranked_list.selectionListDisplay() is the same as

<% if (ranked_list.selection().length == 1) { %>
    <%= ranked_list.selection()[0].label %>
<% } else if (ranked_list.selection().length > 1) { %>
    <%= ranked_list.selection() | toSentenceSerial %>
<% } else { %>
    All <%=ranked_list.metadata(ranked_list.selectionType(),'plural')%>
<% } %>
```

### selectionCount

Provides the number of selected items of the slice with slug &lt;slug&gt;.

```text
ranked_list.selectionCount()
// Is same as: ranked_list.selection().length
```

### selectionType

Provides the group\_by\_type of the current data set.

```text
ranked_list.selectionType()
```

### selectionId

Provides the id of the first selected item.

```text
ranked_list.selectionId()
```

### data \(templates\)

Provides the data items in the current data set in the same format as `<slug>.selection()`.

### dataCount

Provides the number of data items in the current data set.

```text
ranked_list.dataCount()
// Is the same as: ranked_list.data().length
```

### dataCountDisplay\(threshold\)

Provides a formatted string of the number of data items in the response of the slug with slug &lt;slug&gt; for display. If given a threshold, will short format the number if the number exceeds the threshold.

```text
details_table.dataCountDisplay()
details_table.dataCountDisplay(1000)
```

### dataCountWithDimensionDisplay\(threshold\)

Provides a formatted string of the number of data items in the response of the slug with slug &lt;slug&gt; for display. If given a threshold, will short format the number if the number exceeds the threshold. The number string is suffixed with the `group_by_type` of the current data set.

```text
details_table.dataCountWithDimensionDisplay()
details_table.dataCountWithDimensionDisplay(1000)
// is the same as
<%
  var count = details_table.dataCount();
  var suffix = '';
  if (count == 1) {
    suffix = details_table.metadata(details_table.selectionType(), 'singular');
  }
  else {
    suffix = details_table.metadata(details_table.selectionType(), 'plural');
  }
  var s = details_table.dataCountDisplay() + ' ' + suffix;
  s = s.trim();
%>
Review Overall Score for your <%= s|emphasis %>
```

## Filters

Filters can be applied to any string or value and will modify that value. Dunderscore templates support all filters defined here \([http://gabceb.github.io/underscore.string.site/](http://gabceb.github.io/underscore.string.site/)\).

### \|emphasis

Surrounds text with `<strong>` and `</strong>` tags.

### \|noemphasis

Removes emphasized text. All the built-in `display{*}` functions are automatically emphasized. You can turn this off with \|noemphasis.

For instance,

```text
There are <%= ranked_list.selectionDisplay()|noemphasis %> users.
```

### \|prefix:s

Prefixes text with the string s

For instance,

```text
There are <%= ranked_list.dataCount()|prefix:'$' %> users.
// "There are $1000 users"
```

### \|toSentence

Joins an array into a human readable sentence.

```text
<%= ranked_list.selection()|toSentence %>
"a, b and c"
```

## About emphasis

Dunderscore will emphasize template results using the following rules.

* Every interpolate that displays a string will have an automatic emphasis modifier applied to it which runs last. This modifier wraps the string in a strong tag like `<strong>CONTENT</strong>`.
* If a modifier value\|noemphasis is present, the emphasis modifier will not be applied.
* If emphasis and noemphasis are both used \(regardless of in which order they appear\), no emphasis will show up. For instance, if a template was `<%= datum.value|emphasis|noemphasis|emphasis %>` there will be no emphasis on the output.

## Ways of formatting numbers in templates

If we had

```text
// Datum is the following
{ "value": 0.1234,
  "salesValue", 1234.568,
  "valueProp": "salesValue",
  "formatField": "sales" }

// Metadata is the following
{ "foo": { "format": "0.2f" },
  "sales": { "format": "$0.2f" },
  "value": { "format": "0.2%" },
  }
```

<table>
  <thead>
    <tr>
      <th style="text-align:left"><code>&lt;%= datum.value|format:&apos;0%&apos; %&gt; of viewers</code>:</th>
      <th
      style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">Take the value property of datum and format it as percentage with no decimal
        points.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;%= datum.format(&apos;value&apos;, &apos;0%&apos;) %&gt; of viewers</code>:</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Take the value property of datum and format as with no decimal points.
          This is exactly the same as the previous template.</p>
        <p>The result would be: <code>12% of viewers</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;%= datum.format(&apos;value&apos;) %&gt; of viewers</code>:</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Take the value property of datum and format it using the metadata.value
          .format (which is &#x201C;0.2%&#x201D; in this example.</p>
        <p>The result would be: <code>12.34% of viewers</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;%= datum.format(&apos;value&apos;, null, &apos;foo&apos;) %&gt; of viewers</code>:</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Take the value property of datum (0.1234) and format it using the <code>metadata.foo.format</code> (&#x201C;0.2f&#x201D;).
          The null can be anything falsey.</p>
        <p>The result would be: <code>0.12 of viewers</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;%= datum.format(&apos;value&apos;, null, datum.formatField) %&gt; of viewers</code>:</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Take the value property of datum (0.1234) and format it using the <code>metadata[datum.formatField].format</code> (&#x201C;$0.2f&#x201D;)</p>
        <p>The result would be: <code>$0.12 of viewers</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;%= datum.format(datum.valueProp) %&gt; of viewers</code>:</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">Take the valueProp string of the datum and get that property FROM the
        datum and format it using metadata[datum.valueProp].format. So if datum
        .valueProp is &#x201C;foo&#x201D;, this is the same as &lt;%= datum.format(&#x2018;foo&#x2019;)
        %&gt;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;%= datum.value|format %&gt; of viewers</code>:</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Note</p>
        <p>DOES NOT WORK, but could someday :-) Would be same as <code>&lt;%= datum.format(&apos;value&apos;) %&gt; of viewers</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>&lt;%= datum.value|format:datum.formatString %&gt; of viewers</code>:</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Danger</p>
        <p>This doesn&#x2019;t work :-|</p>
      </td>
    </tr>
  </tbody>
</table>## Examples

Display the current selection of a slice.

```text
<%= option_chooser2.selectionDisplay() %> breakdown

// Outputs: <strong>Total Sales</strong> breakdown

// In v2 you did: <strong>{{=selection('option_chooser2')}}</strong> breakdown
```

Display the current selection of a slice with different output for different scenarios.

```text
<% if (ranked_list.selectionCount() == 0) { %>
  Student details
<% } else { %>
  Students who missed questions in <%= ranked_list.selectionDisplay() %>
<% } %>

// In v2 you did:
{{= selection('ranked-list',
              {
                placeholders:{
                              'count:0':'Student details',
                              '*':'Students who missed questions in <strong>{=selection("ranked-list")}</strong>'
                              }
              })
}}
```

```text
// Another example
<% if (key_metrics.selectionCount() && key_metrics.selectionId() ==  'expenditures_amount') { %>
  Expenditure Detail
<% } else { %>
  Lead Investigator Detail
<% } %>

// In v2 you did:
{{= selectionWithPlaceholders('key-metrics', {'expenditures_amount': 'Expenditure Detail', '*': 'Lead Investigator Detail'}) }}
```

```text
// Another example
Explore <%= keymetrics_hierarchy.selectionDisplay('metric') %> results for your learners.

// In v2 you did:
Explore <strong>{{= selection('keymetrics-hierarchy', {'dimension': 'metric'}) }}</strong> results for your learners.
```

Take the number of selections in the details table and format it as a comma delimited number.

```text
<%= details_table.selectionCount()|format:",.0f" %>

// In v2 you did:
{{= selectionsCount('details-table') }}
```

Get the type of selection chosen in the ranked list slice and format it using the metadata plural value for that selection type.

```text
Pick <%= rankedlist.metadata(rankedlist.selectionType(), 'plural')|emphasis %>
that interest you, or choose another grouping.

// In v2 you did:
Pick <strong>{{=dimension()}}</strong> that interest you, or choose another grouping.
```

Show a nicely formatted list of the selected items in the table slice.

```text
Review <%= keymetrics_hierarchy.selectionDisplay() %> for your <%= details_table.dataCountWithDimensionDisplay() %>.

// In v2 you did:
Review <strong>{{= selection('keymetrics-hierarchy', {'dimension': 'metric'}) }}</strong> for your
<strong>{{= itemsCount('self') }}</strong>.
```

```text
// Another example
We found <i class='icon icon-user'></i> <%= details_table.dataCountWithDimensionDisplay(1000) %>

// In v2 you did:
We found <i class='icon icon-user'></i> {{=itemsCountWithThreshold('self', 1000) }}
```

An option chooser item template.

```text
<div data-id="<%= datum.id %>" data-label="<%= datum.label %>" class="group-container__item">
    <div class="group-container__item__value">
        <%= datum.format('value','0%') %> of viewers
    </div>
    <div class="group-container__item__label">
        consumed <%= datum.season %> <%= datum.label %>
    </div>
    <div class="group-container__item__avg">
        Network Average is <%= datum.format('network_average',',.0%') %>
    </div>
</div>

// In v2 you did:
<div data-id="{{=id}}" data-label="{{=label}}" class="group-container__item">
  <div class="group-container__item__value">{{=format('value','0%')}} of viewers</div>
  <div class="group-container__item__label">consumed {{=season}} {{=label}}</div>
  <div class="group-container__item__avg">Network Average is {{=format('network_average','0%')}}</div>
</div>
```

