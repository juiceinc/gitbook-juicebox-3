---
description: 'Comments and discussions on apps, and how to set them up'
---

# Discussions \(almost done. just needs some screenshots\)

Setting up Discussions within your app will allow your users to leave comments within the app so they can have... well... a discussion with other users. 

## Turn On Discussions

In the [app.yaml](../../reference-guide-contents/app.yaml.md), you can set the `use_discussions` field to `true`. This will allow app users to leave comments within the app and so that other users can see their thoughts/ideas. This is a required field in the app.yaml, and should already be in your app when the app is created.

## Authorizing and Compartmentalizing User Discussions

Taking it a step further, you can then add the optional field `discussions_group_property` and set the value to a property on the `user.extra`. This makes it so that users who share the same `discussions_group_property` values within the `user.extra` can see their comments within the app, but nothing outside of that scope. 

{% hint style="info" %}
Here's an example of how `discussions_group_property` would be used. Let's say you have an app that explores data on upcoming NBA draft picks. Team coaches use your app to prepare their strategy for their draft picks. Coaches within a team want to use Discussions to discuss and collaborate, but they definitely don't want coaches outside the team to see their discussions. 

To make this work in the app, you first add a property to the user.extra called \`team\`, and set the value for the \`team\` for each user to that user's team. For example, if \[famous coach\] was a user, his user.extra would look like this:

\[insert screenshot\]

Next, you set the discussions\_group\_property to \`team\` like so:

\[insert screenshot\]

Once you've set the team property in the user.extra and set the discussions\_group\_property to \`team\`, a user will only see the Discussions from users that are on the same team.
{% endhint %}



