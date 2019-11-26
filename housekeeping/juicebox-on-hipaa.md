# Juicebox on HIPAA

What you need to know about building Juiceboxes in a HIPAA environment.

## Background on HIPAA

HIPAA requires us to be able to track who is seeing what and use a subset of Amazon Web Services.

## Caching

Caching is not available and should not be used in HIPAA environments. Recipe responses will not be cached like they are in regular Juicebox apps.

## Anonymizing apps

Anonymization is limited in HIPAA environments because the existing anonymization depends heavily on caching to maintain consistent mappings of what values are mapped to what. For instance, if you have a user named “Cookie Monster”, that user will be renamed everywhere to a consistent anonymized value \(say “Count Dracula”\).

### Option 1: An anonymous dataset

Build a separate dataset containing anonymized raw data and run the app as normal.

### Option 2: Consistent formatters

A second option is to mimic how the existing formatters work but use consistent formatters that always return the same output. For instance, this hospital formatter returns the initials of the actual hospital and the word “Hospital”.

```text
def hospital_formatter(value):
    """ >>> hospital_formatter("St Marks Hospital")
    "SMH Hospital" """
    initials = [w[0].upper() for w in value.split(' ')]
    return ''.join(initials) + ' Hospital'
```

In `build_request_params()` check if the current user is a demo user and add or remove the formatter to rename the hospital. This will have to happen for each Dimension that you use in your app.

```text
def build_request_params(self, *args, **kwargs):
    super(MyService, self).build_request_params(*args, **kwargs)
    if self.request.user.is_demo_user:
        hospital = self.dimension_shelf['hospital']
        if hospital_formatter not in hospital.formatters:
            hospital.formatters.append(hospital_formatter)
    else:
        if hospital_formatter in hospital.formatters:
            hospital.formatters.remove(hospital_formatter)
```

## Logging

We need to be able to log who sees what in a HIPAA environment.

