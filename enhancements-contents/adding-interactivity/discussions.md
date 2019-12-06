---
description: 'Comments and discussions on apps, and how to set them up'
---

# Discussions \(not done. wrapping back after talk w/ people\)

Setting up Discussions within your app will allow your users to leave comments within the app so they can have... well... a discussion with other users. 

## Turn On Discussions

In the [app.yaml](../../reference-guide-contents/app.yaml.md), you can set the `use_discussions` field to `true`. This will allow app users to leave comments within the app and so that other users can see their thoughts/ideas.

## Authorizing and Compartmentalizing User Discussions

Taking it a step further, you can then add the field `discussions_group_property` and set the value to a property on the `user.extra`. This makes it so that users who share the same `discussions_group_property` values within the `user.extra` can see their comments within the app, but nothing outside of that scope. 

{% hint style="info" %}
Take this illustration as an example of when `discussions_group_property` could be useful. Say you create an app that breaks down all of the upcoming draft picks in the NBA and you want to distribute that to all 30 teams, so they can use it to make a more informed decision on their draft picks. You want the personnel on each team to be able to communicate with each other, but not be able to view what other teams are saying about the players. You could have a property in the `user.extra` called 'teams' where the value is which team the person represents, and then it's as easy as stating `discussions_group_property: "team"`in the app.yaml to make sure each person only sees comments made by other people from their team.
{% endhint %}



