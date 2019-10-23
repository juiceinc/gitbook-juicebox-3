# app.yaml

The `app.yaml` file defines application-level settings for a Juicebox app. Here is what a sample app.yaml file looks like.

```text
# Permanently assigned by Juice. Consult your Juice Analytics Representative.
id: "ABCDEFGH"
# The displayed name of this app. Appears on the home page.
label: "My New App"
# Appears in the url for the stack like http://www.juiceboxdata.com/{appslug}/{stackslug}/
slug: "mynewapp"
# Description of this app, appears below the label on the home page.
description: ""
# If true, allow discussions in this app
use_discussions: true
# discussions_group_property is a property of user.extra that controls who
# users can talk to in discussions. If blank, everyone with access to the app
# can discuss together.
# WARNING: IF YOU CHANGE THIS IT WILL RESET ALL DISCUSSIONS USERS ARE FOLLOWING
discussions_group_property: "changeme"
# If true, show help button and allow access to help page.
show_help: false
juicebox_version: "3"
# A list of stacks in this app, should be a folder in the stacks/ directory in this app
stacks:
- "basic"
```

## app.yaml Options

### id

A globally unique id across all Juicebox apps. This will be assigned for you automatically when you run `jb create {appname}`

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | An automatically assigned 8-32 character id | None | No |

### label

The name of your new app. This can be anything you want up to 70 characters.

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | Up to 70 character string | None | No |

### description

An extended description of your app. This will appear on the app home page.

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | Up to 70 character string | None | Yes |

The label and description appear on the home page like this.

[![../../../\_images/Your\_Apps1.png](https://docs.juiceboxdata.com/projects/juicebox/_images/Your_Apps1.png)](https://docs.juiceboxdata.com/projects/juicebox/_images/Your_Apps1.png)

### slug

Appears in the url for the stack like `http://www.juiceboxdata.com/{appslug}/{stackslug}/`. This should be unique among all apps.

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | Up to 70 character string with no spaces | None | No |

### show\_help

Should a help link be displayed for this app. For more about help see Building help.



| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| boolean | true or false | false | No |

### use\_discussions

Are discussions enabled in this app?

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| boolean | true or false | false | No |

### discussions\_group\_property

A property of `user.extra` that controls who users can talk to in discussions. If blank, everyone with access to the app can discuss together. Only users who share the same `discussions_group_property`value in their `user.extra` can share discussions.

The default value is set so that users can not share discussions.

{% hint style="warning" %}
If you change this it resets all discussions users are following.
{% endhint %}

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | A property that should exist on user.extra. If an empty string, all users that can access an app share discussions with each other. | "changeme" | No |

### juicebox\_version

What file layout and engine does this Juicebox application run against.

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | "3", "4" | None | No |

For more details see [Juicebox file structure](juicebox-file-structure.md).

### is\_public

{% hint style="warning" %}
Public apps **do not** support discussions or `user.extra` based data permissions.
{% endhint %}

Is this app **public**. This makes it available to anyone who hits the url without requiring them to be logged in.

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| boolean | true or false | false | Yes |

### footer

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| string | HTML text | "" \(an empty string\) | No |

A footer is added at the bottom of every app that shows both the version of Juicebox being run, as well as an app version if it has been set up in the `app.yaml` metadata config.

{% hint style="info" %}
When the footer is customized,  “Powered by Juicebox” disappears. 
{% endhint %}

### stacks

| Type | Allowed values | Default | Optional |
| :--- | :--- | :--- | :--- |
| list of strings | Strings must be valid stack directories that exist within the projects stacks/ directory. | None | No |

A list of directories containing stack definitions that you want to appear in this app. See more: [Stacks](https://docs.juiceboxdata.com/projects/juicebox/topics/juicebox_reference/stacks/index.html#stacks).

| Optional: | No |
| :--- | :--- |
| Values: | A YAML list of stacks |
| Example: |  |



