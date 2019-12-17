# Slices

## Defining Slices

Slices are defined in a list the `stack.yaml` \(see: [stack.yaml slices](../stack.yaml.md#slices)\). Slices are displayed on the stack’s web page in top-down order based on their position in the `stack.yaml`.

Slices are powered by either a data service or a JSON file found in the stack’s `fixtures` directory. 

Many slices support configuration options that change the visual appearance and function of the slice. The `config` options of each slice vary by the slice type. Details on each slice's `config` options can be found in the [slice docs](http://dev.fruitiondata.com/static/docs/slices.html). 

Here's an example slice definition in `stack.yaml` that is powered by a data service:

```yaml
- slice_type: "option-chooser"
  slug: "option-chooser-1"
  title: "This should go away"
  config: {}
  data_service: "basicservice.FirstChooserV3Service"
```

