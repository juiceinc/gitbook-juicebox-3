# Customizing slice templates

Slices are created using templates. These templates can be overridden on a slice-by-slice basis by providing custom templates in `slice.config`

{% hint style="warning" %}
While templates can be used to customize your slice's appearance, it is better to use builtin configuration options.

Consider using [slice.layout](../../reference-guide-contents/slices/slices-and-common-configuration.md#layout), [slice.config.layout](../../reference-guide-contents/slices/slices-and-common-configuration.md) or [slice.config.layoutFlags](../../reference-guide-contents/slices/slices-and-common-configuration.md#config-layoutflags) to get the appearance you need.
{% endhint %}

Here are the slice.config templates you can customize. Check with your Juicebox representative to see what a starting template would look like.

## config.baseTemplate

Slice base template name selector.

| Optional: | yes, default is “\#base-slice-template” |
| :--- | :--- |
| Values: | The id of a template in `templates.html` |
| Example: |  |

## config.searchTemplate

The template for the slice search box.

| Optional: | yes, default is “\#base-slice-search-template” |
| :--- | :--- |
| Values: | The id of a template in `templates.html` |
| Example: |  |

## config.notesTemplate

The template for the slice notes.

| Optional: | yes, default is “\#base-slice-notes-template” |
| :--- | :--- |
| Values: | The id of a template in `templates.html` |
| Example: |  |

## config.legendTemplate

Slice legend template name selector.

| Optional: | yes, default is “\#base-slice-legend-template” |
| :--- | :--- |
| Values: | The id of a template in `templates.html` |
| Example: |  |

## config.datasetsTemplate

The template for the list of slice datasets/responses.

| Optional: | Yes, default is “\#base-slice-datasets-template” |
| :--- | :--- |
| Values: | The id of a template in `templates.html` |
| Example: |  |

## config.bodyTemplate

The template for the slice body.

| Optional: | Yes, default is “\#base-slice-body-template” |
| :--- | :--- |
| Values: | The id of a template in `templates.html` |
| Example: |  |

## config.controlsTemplate

The template for the slice control buttons.

| Optional: | yes, default is “\#base-slice-controls-template” |
| :--- | :--- |
| Values: | The id of a template in `templates.html` |
| Example: |  |

## 

