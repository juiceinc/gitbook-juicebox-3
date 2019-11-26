# stack.yaml

The stack.yaml file defines stack-level settings for a Juicebox app. 

Here is what a sample stack.yaml file looks like.

```text
# Label is the displayed name of this stack
label: "Knowledge"

# Provides optional text for the story chooser slice to describe this stack
description: "An overview of the Knowledge survey data"

# The optional fontawesome icon to use with the stack label in the story chooser
icon: "close"

# Settings for the background of the story chooser card for this stack (not the stack itself)
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
            
# Should a hopscotch tour be displayed.
has_tour: false

# The hash to load if the user hasn't started using this stack.
# If you leave this blank the slices will start with nothing
# selected or default selections.
initial_hash: ""

# For more on setting page background and header, see
# http://docs/projects/juicebox/topics/styling/backgrounds.html#
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

# Default start slice lists the slug of a given slice, establishing that slice as the default starting
# view for a given stack
default_start_slice: "ranked-list-title"

slices:
  # Slice documentation: http://docs/projects/juicebox/topics/slices/index.html
  # How to build titles and templates: http://docs/projects/juicebox/topics/slices/templates.html
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



## stack.yaml options

Let’s talk about what’s in the stack.yaml file.

### label

The name of this stack. This can be anything you want up to 70 characters.

| Optional: | No |
| :--- | :--- |
| Values: | An up to 70 character string |
| Example: | `label: "Knoweldge"` |

### description

Description of this story, appears below the label on story choosers.

| Optional: | Yes |
| :--- | :--- |
| Values: | A string |
| Example: | `description: "An overview of the Knowledge survey data"` |

### icon

A font-awesome icon that represents this stack.

| Optional: | Yes |
| :--- | :--- |
| Values: | An up to 70 character string |
| Example: | `icon: "close"` |

### story\_theme

A json object that controls story specific theming.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Optional:</th>
      <th style="text-align:left">Yes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Values:</td>
      <td style="text-align:left">A dictionary</td>
    </tr>
    <tr>
      <td style="text-align:left">Example:</td>
      <td style="text-align:left">
        <p><code>image: &apos;backgrounds/pattern.jpg&apos;</code>
        </p>
        <p><code>    color: &quot;#FFFFFF&quot;</code>
        </p>
        <p><code>    config:</code>
        </p>
        <p><code>        exp: -1</code>
        </p>
        <p><code>        w: 300</code>
        </p>
      </td>
    </tr>
  </tbody>
</table>### has\_tour

Does this stack have tours in the help directory? These are yaml files that in the help directory. If so, they will be loaded and will display for this stack.

| Optional: | Yes, default is false |
| :--- | :--- |
| Values: | true\|false |
| Example: | `has_tour: false` |

### background

A background or backgrounds for this stack.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Optional:</th>
      <th style="text-align:left">Yes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Values:</td>
      <td style="text-align:left">A background as defined in <a href="../../../enhancements-contents/styling-and-formatting/untitled-1.md#styling-backgrounds">Styling Backgrounds</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Example:</td>
      <td style="text-align:left">
        <p></p>
        <p></p>
        <p><code>background:</code>
        </p>
        <p><code>  - gradient: &apos;linear-gradient(to bottom, rgba(0,0,0,0) , rgba(0,0,0,1))&apos;</code>
        </p>
        <p><code>  - image: &apos;backgrounds/pattern.jpg&apos;</code>
        </p>
        <p><code>    extra: &quot;0 100px&quot;</code>
        </p>
        <p><code>    config:</code>
        </p>
        <p><code>      w: 1920</code>
        </p>
        <p><code>      sepia: 100</code>
        </p>
        <p><code>      con: -40</code>
        </p>
        <p></p>
        <p></p>
      </td>
    </tr>
  </tbody>
</table>### global\_filters\_service

A data\_service definition for the global filters. If this is missing, no global filters will appear.

| Optional: | No |
| :--- | :--- |
| Values: | A package and class name for the global filters data service |
| Example: | `global_filters_service: basicservice.FilterService` |

### initial\_hash

A “getting started” hashr hash that defines what people should see the very first time they open this stack. If an initial\_hash value is set, the Reset button will appear next to the global filters pill.

| Optional: | No, default is an empty string |
| :--- | :--- |
| Values: | A hash for this stack. |
| Example: | `initial_hash: ""` |

### slices

A list of slice definitions, see [Defining Slices](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/slices/creating_slices.html#defining-slices)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Optional:</th>
      <th style="text-align:left">No</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Values:</td>
      <td style="text-align:left">A YAML list of slices that appear in this stack.</td>
    </tr>
    <tr>
      <td style="text-align:left">Example:</td>
      <td style="text-align:left">
        <p><code>slices:</code>
        </p>
        <p><code>- slice_type: &quot;ranked-list&quot;</code>
        </p>
        <p><code>  title: &quot;This is my title&quot;</code>
        </p>
        <p><code>  config: {}</code>
        </p>
        <p><code>  data_service: basicservice.RankedListService</code>
        </p>
      </td>
    </tr>
  </tbody>
</table>