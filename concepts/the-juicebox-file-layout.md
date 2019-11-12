---
description: Juicebox 3 and 4 file structure and layout
---

# The Juicebox File Layout

There are currently two versions of Juicebox in production, version 3 and version 4. While they use the same kernel code, they have different layouts and core concepts on structure. This section shows the difference between the two.

{% hint style="info" %}
Check which version your app is running in the **app.yaml file**.   
_juicebox\_version: '4' \(or\) '3'_
{% endhint %}



## Version 3

Version 3 is designed so that each stack directory contains all resources needed for that stack.

```text
app.yaml                   App details, list of stacks to display
theme.yaml                 Defines logo, css
help/                      Markdown or html help
public/                    Contains images used in the app
stacks/
    {stack_name}/
        stack.yaml         Stack and slice definitions.
        templates.html     Custom templates used by this stack.
        dataservice.py     Dynamic data services for this stack.
        fixtures/
        help/              Stack specific help and tour definition files.
```

## Version 4

With version 4, “stacks” have been renamed to “stories”. The file structure has been simplified to allow visual theming reuse and to consolidate all data service code in a single place.

```text
app.yaml                  App details and list of stories to display
help.md or help.html      Application help
theme/
    theme.yaml            Theme logo and parentage
    variables.scss        Theme variables
    styles.scss           Custom css to apply to slices
    img/                  Image assets to use as slice backgorunds
    templates/            Custom html templates
stories/
    {story_name}.yaml     Story and slice definitions.
public/                   Additional public assets that the app may rely
                          on. For instance, custom javascript code.
data_services/            Dynamic data service code for all stories
```

## Converting from version 3 to version 4

A conversion script will allow version 3 apps to be rewritten as version 4 apps. This conversion script will be available in spring 2019.

**Theme**

* variables.scss are moved from theme.yaml and placed in their own file for easier editing.
* All templates are moved from templates.html in stacks to individual files named after each template.
* Slice `extra_css` is converted to a class that can be applied to any slice in the entire app. It’s now possible to re-use theming code across slices.
* Images that were used as slice or story backgrounds are now stored with the theme rather than in public/
* Application footer content is now part of the theme.yaml.

**Stories**

* `Stack.yaml` is now renamed as `{story_name}.yaml`
* Tours are moved from individual yaml files in `stack/{stack_name}/help/{tour_name}.yaml` to `story.yaml`.

**Help**

* Stack level help doesn’t exist. All help is in a markdown or html file at the top level of the app.

