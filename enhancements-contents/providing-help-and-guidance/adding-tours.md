# Adding Tours

## Enabling stack tours

For tours to be displayed [has\_tour](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/stacks/index.html#has-tour) needs to be `true` in [Stacks](../../reference-guide-contents/stacks/stack.yaml/).

## Building stack tours

Tours are defined in yaml files in a stack’s `help/` directory. These tours get loaded and displayed for a stack on the top of the stack page.

A Tour yaml file holds a definition for a Hopscotch tour. Hopscotch is a [framework](http://linkedin.github.io/hopscotch/) created by LinkedIn to help create tours.

```text
# A unique id for a tour. Feature tours should start with 'feature-', stack tours should start with 'stack-'
id: "stack-ranked-list-2-guide-me"
# The name for the tour. Appears in the drop-down list of tours
name: "Welcome to the new Ranked List slice"
# Set this to the current time when saving changes to the tour which would warrant a user seeing it again.
updated: 2017-10-31 17:34:47.702913+00:00
# If false, tour will only appear when new or updated for the user.
show_all_the_time: true
# JSON definition for Hopscotch tour
definition:
- "yOffset": 20
  "content": "Welcome to the new Ranked List slice!"
  "placement": "top"
  "target": ".slug-rl2"
  "title": "Ranked List Tour"
```

### id

An unique id for a tour. All stack tour ids must start with the string ‘stack-‘.

| Optional: | No |
| :--- | :--- |
| Values: | An up to 70 character string that must start with ‘stack-‘ |
| Example: |  |

### name

The name of the tour. This name will appear in the drop-down list of tours if the stack has more than one tour.

| Optional: | No |
| :--- | :--- |
| Values: | An up to 200 character string |
| Example: |  |

### updated

A timestamp for when the tour was updated. Set this to the current time when saving changes to the tour which would warrant a user seeing it again.

| Optional: | No |
| :--- | :--- |
| Values: | A timestamp in the format YYYY-MM-DD HH:MM:SS |
| Example: |  |

### show\_all\_the\_time

A flag that indicates if the tour should always show up in the drop down list of tours. If `false`, the tour will only appear when new or updated.

| Optional: | Yes, default is true |
| :--- | :--- |
| Values: | boolean, true or false |
| Example: |  |

### definition

The JSON definition for the Hopscotch tour. The most basic tour has the following definition:

| Optional: | No |
| :--- | :--- |
| Values: | A JSON definition of the tour. |
| Example: |  |

## Triggering tours from slices

Sometimes users want more explanation when they’re directly looking at a slice. We now provide a way to launch a specific tour from a slice.

This is provided by adding a link called “GUIDE ME” in the top-left corner of the slice \(next to where the legend shows up\). The link is enabled by providing the id of a tour as the `guide` for a slice.:

```text
- slice_type: "free-form"
  slug: "overview"
  title: "Overview"
  guide: "stack-welcome-tour"
```

The location of the link can be changed with the slice’s [layout](../../reference-guide-contents/slices/slices-and-common-configuration.md#layout) config option in [Common slice configuration](../../reference-guide-contents/slices/slices-and-common-configuration.md).

```text
- slice_type: "free-form"
  slug: "overview"
  title: "Overview"
  guide: "stack-welcome-tour"
  config:
    layout:
      "top-right": ["guide", "search"]
```

The default label of the link \(“GUIDE ME”\) can be also be changed with the `guideLabel` option:

```text
- slice_type: "free-form"
  slug: "overview"
  title: "Overview"
  guide: "stack-welcome-tour"
  guideLabel: "Take a tour"
```

