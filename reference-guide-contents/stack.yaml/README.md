# Stacks \(done\)

## stacks/ Directory Layout

The stacks/ directory contains one or more stack definitions. A stack definition consists of:

| File/Directory | Definition | Optional |
| :--- | :--- | :--- |
| stack.yaml | Defines and configures the slices in the story | No  |
| templates.html | Defines custom html templates to use in slices. | Yes, can be omitted if no custom templates are used. |
| dataservices.py | Contains one or more data services that provide data to slices. The name of this file can be any valid python file name. | Yes, can be omitted if **only** fixture data is used for slices  |
| fixtures/ | A directory containing data service fixtures to use for slices. Fixtures are json files that provide unchanging Juicebox responses | Yes, can be omitted if **no fixture data** is used. |
| help/ | A directory containing tour definition yaml files.  | Yes, can be omitted of no tours are used in the slice. |

Each stack tells a self-contained data story. When the user reaches the end of the story, a Story Chooser allows them to decide what they want to see next.

## stack.yaml Options

The stack.yaml file defines stack-level settings for a Juicebox app. 

Here is what a sample stack.yaml file looks like.

```text
label: "Knowledge"

description: "An overview of the Knowledge survey data"

icon: "close"

story_theme:
    # The text can be changed to be either light or dark
    text_color: "light"
    background:
        # An image may be used
        image: 'backgrounds/pattern.jpg'
        # Or a color
        color: "#FFFFFF"
        # The background can be configured with imgix api parameters
        config:
            exp: -1
            w: 300
            
has_tour: false

initial_hash: ""

# Images can be urls or files located in public/img/
background:
  - gradient: 'linear-gradient(to bottom, rgba(0,0,0,0) , rgba(0,0,0,1))'
  - image: 'backgrounds/pattern.jpg'
    extra: "0 100px"
    config:
      w: 1920
      sepia: 100
      con: -40
header:
  color: '#006699'
  
# Provides data to the global filters
# Can be either a data service class in your service.py file (e.g. 'realtorservice.FilterService')
# or a json file in the fixtures directory (e.g. 'filters.json')
global_filters_service: basicservice.FilterService

default_start_slice: "ranked-list-title"

slices:
  - slice_type: "ranked-list"
    # The title line for the slice.
    title: 'This is my title'
    slug: 'ranked-list-title"
    # Detailed configuration for the slice.
    config: {}
    # Provides data to the slice
    # Can be either a data service class in your service.py file (e.g. 'realtorservice.RankedListService')
    # or a json file in the fixtures directory (e.g. 'rankedlist.json')
    data_service: basicservice.RankedListService
```

| Key | Optional | Value | Definition |
| :--- | :--- | :--- | :--- |
| label | No | &lt;= 70 character string | The name of this stack. This can be anything you want up to 70 characters. |
| description | Yes | A string | Description of this story, appears below the label on story choosers. |
| icon | Yes | &lt;= 70 character string | A font-awesome icon that represents this stack. |
| story\_theme | Yes | A dictionary | A json object that controls story specific theming. |
| has\_tour | Yes, default is false | true\|false | Does this stack have tours in the help directory? These are yaml files that in the help directory. If so, they will be loaded and will display for this stack. |
| background | Yes | A background as defined in [Styling Backgrounds](../../where-should-i-live/applying-backgrounds-to-stacks-and-slices.md#styling-backgrounds) | The background or backgrounds for this stack. |
| header | Yes | A background as defined in [Styling Backgrounds](../../where-should-i-live/applying-backgrounds-to-stacks-and-slices.md#styling-backgrounds) | A background to show in the header of this stack. |
| global\_filters\_service | No | A package and class name for the global filters data service | A [data\_service](../slices/slices-and-common-configuration.md#data_service) definition for the global filters. If this is missing, no global filters will appear. |
| initial\_hash | No, default is empty string | A hash for this stack. | A “getting started” hashr hash that defines what people should see the very first time they open this stack. If an initial\_hash value is set, the Reset button will appear next to the global filters pill. |
| slices \(stack\) | No | A YAML list of slices that appear in this stack. | A list of slice definitions, see [Defining Slices](../slices/defining-slices.md) |

