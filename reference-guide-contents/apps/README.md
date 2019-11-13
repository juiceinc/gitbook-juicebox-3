# Apps

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
# What version of juicebox core should this app use? Choices are "2" or "3"
# "2" is the default
juicebox_version: "3"
# A list of stacks in this app, should be a folder in the stacks/ directory in this app
stacks:
- "basic"
```

## app.yaml Options

### id \(app.yaml\)

A globally unique id across all Juicebox apps. This will be assigned for you automatically when you run `jb create {appname}`

| Optional: | No |
| :--- | :--- |
| Values: | An 8 character string |
| Example: |  |

### label \(app.yaml\)

The name of your new app. This can be anything you want up to 70 characters.

| Optional: | No |
| :--- | :--- |
| Values: | An up to 70 character string |
| Example: |  |

### description

An extended description of your app. This will appear on the app home page.

| Optional: | No |
| :--- | :--- |
| Values: | An up to 70 character string with no spaces \(but it’s better if its short\) |
| Example: |  |

The label and description appear on the home page like this.

### slug

Appears in the url for the stack like `http://www.juiceboxdata.com/{appslug}/{stackslug}/`. This should be unique among all apps.

| Optional: | No |
| :--- | :--- |
| Values: | An up to 70 character string with no spaces \(but it’s better if its short\) |
| Example: |  |

### metadata

Metadata provides extra configuration for this application. The following options are supported.

`version`: A semantic version number for this Juicebox app. This may be maintained using a tool like `bumpversion`.

`commands`: Configuration for commands. Each command will be a key. For more see [Configuring commands](https://docs.juiceboxdata.com/projects/juicebox/topics/interactivity/slice_commands.html#configuring-commands).

`logging`: Configuration for application logging. If the logging block contains a Sentry DSN \([https://docs.sentry.io/quickstart](https://docs.sentry.io/quickstart)\), data service errors that occur will be logged to that endpoint.

`invitations`: Configuration for invitations to this app. `subject` and `body` will appear in an email when a user is invited to this app.

`auto_inject_story_chooser`: A flag to indicate if the story-chooser slice should be automatically injected in all the stacks for this app. Defaults to `false`.

`embed`: An object containing config for app embedding. Currently we have only one configuration `link_duration` – expiration time of embed urls, in seconds\(default=60\).

| Optional: | Yes |
| :--- | :--- |
| Values: | An object containing configuration. |
| Example: |  |

### show\_help

Should a help link be displayed for this app. For more about help see [Building help](https://docs.juiceboxdata.com/projects/juicebox/topics/guidance/help.html#building-help).

| Optional: | No |
| :--- | :--- |
| Values: | true\|false |
| Example: |  |

### use\_discussions

Are discussions enabled in this app?

| Optional: | No |
| :--- | :--- |
| Values: | true\|false |
| Example: |  |

### discussions\_group\_property

A property of `user.extra` that controls who users can talk to in discussions. If blank, everyone with access to the app can discuss together. Only users who share the same `discussions_group_property` value in their user.extra can share discussions.

The default value is set so that users can not share discussions.

Warning

If you change this it resets all discussions users are following.

| Optional: | Yes. This is not needed if use\_discussions is false. |
| :--- | :--- |
| Values: | A property that should exist on user.extra. If an empty string, all users that can access an app share discussions with each other. |
| Example: |  |

### juicebox\_version

What file layout and engine does this Juicebox run against.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Optional:</th>
      <th style="text-align:left">No.</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Values:</td>
      <td style="text-align:left">
        <p>&#x201C;2&#x201D;, &#x201C;3&#x201D; or &#x201C;4&#x201D;. The default
          is &#x201C;3&#x201D;.</p>
        <p>&#x201C;2&#x201D; is deprecated and support will be ended in mid-2019.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Example:</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>For more details see [The Juicebox File Layout](../juicebox-file-structure.md)

### is\_public

Is this app **public**. This makes it available to anyone who hits the url without requiring them to be logged in.

Warning

Public apps **do not** support discussions or `user.extra` based data permissions.

| Optional: | Yes. The default is false |
| :--- | :--- |
| Values: | true\|false |
| Example: |  |

### is\_mobile

Enables an application to be tagged as “mobile”. In this case an extra popup will appear prompting users to save the app to their homescreen on a iOS or Android device.

Warning

The code to support this has not been maintained and iOS and Android have been moving away from supporting homescreen links.

| Optional: | Yes. The default is false |
| :--- | :--- |
| Values: | true\|false |
| Example: |  |

### stacks \(app.yaml\)

A list of directories containing stack definitions that you want to appear in this app. See more: [Stacks](../stacks/).

| Optional: | No |
| :--- | :--- |
| Values: | A YAML list of stacks |
| Example: |  |

