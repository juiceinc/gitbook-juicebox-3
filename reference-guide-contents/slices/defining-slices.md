# Defining Slices \(done\)

A stack is comprised of many slice visualization that provide different parts of the story the data is trying to tell. There are many types of slice visualizations that one can build. You can see a list of all the slices types in our [Slice Reference](../slice-reference/) section. Slices are defined in the `stack.yaml` file in a list as described in the [stack.yaml options](../stack.yaml.md#stack-yaml-options). Slices are displayed on the stack’s web page in top-down order based on their position in the `stack.yaml` file. By default, slice data services “listen” to all the slices above them and filter their data accordingly.

## Defining a Slice

They must inherit from our RecipeService just like our FilterService. They must have a build\_reponse method and optionally they can other method for setting specific options. Depending on your needs. Slices are powered by either a data service or a JSON file found in the stack’s `fixtures` directory. Many slices support configuration options that change the visual appearance and function of the slice. The `config` of each slice varies by the slice type and more details can be found in the [slice docs](../slice-reference/). Let’s take a look at a slice definition in `stack.yaml` that is powered by a data service.

{% tabs %}
{% tab title="stack.yaml slice example" %}
```text
- slice_type: "option-chooser"
  slug: "foo"
  title: "This should go away"
  config: {}
  data_service: "basicservice.FirstChooserV3Service"
```
{% endtab %}
{% endtabs %}

## Providing Data to a Slice

Data services use recipes to build the data responses our slices need to build the visualizations. In most cases, recipes can also render a response themselves for your slice. However, it is also possible to build a custom response as well using the data returned from a recipe.

We start by defining a `build_response` method that specifies how we return data to the visualization slice. This is done by building one or more recipes to get the data, and then using the `.render('NAME')` method on the recipe that can generate a response to be returned to the UI as JSON for use in the filters.

When building a slice service, we prefer to use the `self.metrics` and `self.dimensions` lists to control the Ingredients used in our recipes. Creating these two lists is normally the first step in building a response. With our metrics and dimensions assigned, we are ready to build our recipe. We use the `.recipe()` method on our service \(which comes from one of our inherited bases\), add our metrics and dimensions to it. Since our metrics and dimensions are a list, we use a `*` to expand the list into its individual components. Next, we use the `recipe.render()` method to build the response. The `.render()` method should be supplied a name, and optionally a flavor. The name is used by some slices in the UI, and helps keep different data sets separated in slices that support multiple data sets. The flavor is used when a single slice type can have many different output formats. For example, an OptionChooser slice can be both a horizontal click-able list or a drop down menu.

Here is an example of an OptionChooser slice. We don’t use any dimensions in this slice because we’re not grouping the data in anyway. We’re just looking for summary records.

{% tabs %}
{% tab title="option\_chooser\_example.py" %}
```python
class OptionChooserService(BasicService):
    def build_response(self):
        self.metrics = ('pop2000', 'pop2008', 'popdiff', 'avgage',
                        'pctfemale')
        recipe = self.recipe().metrics(*self.metrics)
        self.response['responses'].append(recipe.render(flavor='metric'))
```
{% endtab %}
{% endtabs %}

There will be more on slice types and flavors in the cookbook section of the Guide. Next, we’ll learn about performing comparisons and blending recipes.

