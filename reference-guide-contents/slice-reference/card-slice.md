---
description: A card slice is used to display record details in a searchable sortable way.
---

# Card \(done\)

## Card config

Card slices support the [Common configuration options for all slices](../slices/slices-and-common-configuration.md). Additional options are:

{% tabs %}
{% tab title="Card config example" %}
```yaml
config:
  cardTemplateName: "#card-template"
  cardWidth: '50%'
  // can also be written like this in the yaml
  // searchFields:
    // - label
    // - score
  searchFields: ['label', 'score']
  sortFields:
    - field: "score"
      label: "Score"
      default: true
      sortDirection: "ascending"
    - field: "count"
      label: "Count"
```
{% endtab %}
{% endtabs %}

| Key | Optional | Values | Description |
| :--- | :--- | :--- | :--- |
| cardTemplateName | No,  If not specified, an empty string is rendered for the card content. | A CSS selector that exists in templates.html | The name of the template that will be used to render the content inside the card. Should start with a \# and be defined in templates.html. |
| cardWidth | Yes, default is 250px | String or Number | The width in pixels/percentage of the card |
| searchFields: | Yes, default is `["label"]` | Array of Strings | The data attributes to be used for searching. |
| sortFields | Yes | An array of objects [described below](card-slice.md#sortfields) | The data attributes to be used for sorting, can specify [{field, label, sortDirection, default}.](card-slice.md#sortfields) |

### sortFields

We saw in the table above that you can use sortFields to bring in custom fields that will allow the user to sort the cards by any number of fields from your ingredients, but let's get into the various ways you can manipulate the fields. The data attributes to be used for sorting, can specify {field, label, sortDirection, default}. check the [card config above](card-slice.md#card-config) for an example of each of these.

`field`: This is the field that you want to sort on. This isn't optional if you are going to use sortFields.

`label`: This is where you can change the displayed name in the sort picker.

`sortDirection`: This is optional. You can sort using the keywords 'ascending', 'descending', or 'natural'. The default `sortDirection` is ascending. if you use natural, it means that no sorting will take place. 

`default`: This will be a boolean value that you will use to say which field you want to be the default field to sort your cards by. The default value for `default` is false, so you only need to really use this when noting which field is true/will be the default.

## Flavors of Card

### Default \(card\)

The default flavor renders the first supplied dimension as the card label, and returns all the metrics and dimensions by name in the response to be used in the template.

![](../../.gitbook/assets/card-default.png)

The code for the default card flavor has three parts to it: python/data service, stack.yaml, and the html template:

{% tabs %}
{% tab title="card\_service.py" %}
```python
class CardV3Service2(CensusService):
    def build_response(self):
        self.metrics = ('popdiff',)
        self.dimensions = ('state',)

        recipe1 = self.recipe().metrics(*self.metrics).dimensions(
            *self.dimensions)

        self.response['responses'].append(recipe.render())
```
{% endtab %}

{% tab title="stack.yaml" %}
```yaml
- slice_type: "card"
  slug: "jam-card1"
  title: "Card"
  config:
    "cardTemplateName": "#jam-card-template"
  data_service: "censusv2service.CardV3Service2"
```
{% endtab %}

{% tab title="templates.html" %}
```markup
<script type="text/template" id="jam-card-template">
  <div class="fr-body2"><%= datum.label %></div>
  <div class="fr-caption"><%= datum.format("popdiff", ',.0f') %> change in population</div>
</script>
```
{% endtab %}
{% endtabs %}

## Mixins

### CardActionPlannerViewMixin \(only used in Healthstream apps\)

This is a mixin that is and will only be used by HSTM apps. The data service for the slice that uses this mixin should pass additional context in the response like this:

{% tabs %}
{% tab title="HSTM Card Mixin" %}
```python
response['templateContext']['defaultItem'] = {'questions': selected_question,
                                    'title': ' ',
                                    'description': description,
                                    'clientident': ci,
                                    'unitident': ui,
                                    'due_date': datetime.now().date(),
                                    'created_by': self.request.user.get_full_name()}
```
{% endtab %}
{% endtabs %}

## Linking to websites or files

You can now add and click on hyperlinks in the card slice and it will not interfere with the selection of the card item.

{% tabs %}
{% tab title="Link to Website/File HTML Example" %}
```markup
<script type="text/template" id="jam-card-template">
  <div class="fr-body2"><%= datum.label %></div>
  <div class="fr-caption"><%= datum.format("popdiff", ',.0f') %> change in population</div>
  <div class="fr-menu">
    <a href="http://www.juiceanalytics.com" target="_blank">Visit website</a>
  </div>
</script>
```
{% endtab %}
{% endtabs %}

