---
description: Let's take a look at how Juicebox 3 apps handle the file structure.
---

# Juicebox 3 File Layout \(done\)

## Layout

Version 3 is designed so that each stack directory contains all resources needed for that stack.

{% tabs %}
{% tab title="V3 Layout" %}
```text
// Subsequent pages will get into more detail about each directory, 
// but this will give you a general idea about each one.

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
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Juicebox 4 is handled quite a bit differently. To see how they are laid out and to learn how to convert Juicebox 3 apps, hop on over to the Juicebox 4 documentation \(Juicebox 4 documentation needs to be link when JB4 docs are done\)
{% endhint %}

