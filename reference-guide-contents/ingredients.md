---
description: Information on the data ingredients we need for our recipes
---

# Ingredients

**Ingredients** are reusable SQLAlchemy snippets used for creating recipes. Once defined, Ingredients can be used across your Juicebox application in as many recipes as you like.

Ingredients can easily be created using yaml.

```text
zip:
    kind: Dimension
    field: zip
    singular: Zipcode
    plural: Zipcodes
total_const_cost:
    kind: Metric
    field: const_cost
    singular: Total Construction Cost
    format: dollar
avg_const_cost:
    kind: Metric
    field:
        value: const_cost
        aggregation: avg
    singular: Avg. Construction Cost
    format: dollar
avg_issue_time:
    kind: DivideMetric
    numerator_field:
        value: date_issued-date_entered
    denominator_field:
        value: permit
        aggregation: count
    singular: 'Avg Issue Time (Days)'
    format: comma
```

The above yaml configuration is equivalent to the ingredient shelves written in Python code below.

```text
shelf = ({
    'zip': Dimension(MyTable.zip, singular='Zipcode', plural='Zipcodes'),
    'total_const_cost': Metric(func.sum(MyTable.const_cost),
    singular='Total Construction Cost',
    format='$,.0f')
    'avg_const_cost': Metric(func.avg(MyTable.const_cost),
    singular='Avg Construction Cost',
    format='$,.0f')
    'avg_issue_time': DivideMetric(func.sum(MyTable.date_issued
            - MyTable.date_entered),
    func.count(MyTable.permit),
    singular='Avg Issue Time (Days)',
    format=',.0f')
})
```

## Fields

Consider `field: zip`.

This represents a database column, [`zip`](https://docs.python.org/3/library/functions.html#zip), in whatever table this shelf is using. Another way of representing the same thing is:

We use this object expression when we need to add modifiers to the field. Two such modifiers are **aggregations** and **conditions**.

## Aggregations

```text
field:
    value: zip
    aggregation: sum
```

The above is equivalent to `func.sum(MyTable.zip)`, which should look familiar if you are used to configuring ingredient shelves in Python.

There are many built-in aggregations \( [`None`](https://docs.python.org/3/library/constants.html#None) means the field isn’t aggregated\).

| sum: | `func.sum` |
| :--- | :--- |
| min: | `func.min` |
| max: | `func.max` |
| avg: | `func.avg` |
| count: | `func.count` |
| count\_distinct: | `lambda fld: func.count(distinct(fld))` |
| month: | `lambda fld: func.date_trunc('month', fld)` |
| week: | `lambda fld: func.date_trunc('week', fld)` |
| year: | `lambda fld: func.date_trunc('year', fld)` |
| quarter: | `lambda fld: func.date_trunc('quarter', fld)` |
| None: | `lambda fld: fld` |

## Conditions

Conditions compare a field against an expression.

For example:

```text
condition:
    field: last_name
    in: ['Jones', 'Punjabi']
```

This specifies the ingredient should match cases where the database column `last_name` is one of either ‘Jones’ or ‘Punjabi’.

```text
field:
    value: zip
    condition:
        field: last_name
        in: ['Jones', 'Punjabi']
```

The above yields the following SQL:

```text
case when mytable.last_name in ('Jones', 'Punjabi') then mytable.zip end
```

In SQLAlchemy, it is expressed with a case function and a blizzard of ‘\(‘ and ‘\)’.

## Field Math

A field value can contain columns that are added and subtracted from each other.

```text
field:
    value: sales - tax
```

… is the same as `func.sum(MyTable.sales - MyTable.tax)`

## Combining & Nesting

Conditions, aggregations and fields can be combined.

```text
field:
    value: age
    aggregation: avg
    condition:
        field: last_name
        in: ['Jones', 'Punjabi']
```

…results in the SQL

```text
avg(case when mytable.last_name in ('Jones', 'Punjabi') then mytable.age end)
```

## Metrics

Metrics are automatically aggregated by sum. You can supply a different aggregation explicitly.

```text
sales:
kind: Metric
field: sales_dollars
```

…will give you this

```text
shelf = Shelf({
'sales': Metric(func.sum(MyTable.sales_dollars))
})
```

If you want to specify a different aggregation, do this:

```text
avg_sales:
kind: Metric
field:
    value: sales_dollars
    aggregation: avg
```

… which will give you

```text
shelf = Shelf({
'avg_sales': Metric(func.avg(MyTable.sales_dollars))
})
```

## Performing safe division

Metrics can divide a field by another field in a safe way by using `divide_by`.

```text
sales_per_person:
    kind: Metric
    field: sales_dollars
    divide_by:
        field:
            value: person_id
            aggregation: count_distinct
```

## Referring to other metrics

Fields can contain references to other fields. For instance you might want to divide one metric by another. Refer to other metrics by prefixing the metric id with a `@`.

```text
total_sales:
    kind: Metric
    field: sales_dollars
total_people:
    field:
        value: person_id
        aggregation: count_distinct
sales_per_person:
    kind: Metric
    field: '@total_sales'
    divide_by: '@total_people'
```

## Dimensions

Dimensions can optionally supply a id\_field and a lookup.

```text
zip:
    kind: Dimension
    field: zip
    singular: Zipcode
    plural: Zipcodes
```

… is the same as

```text
shelf = Shelf({
'zip': Dimension(MyTable.zip, singular='Zipcode', plural='Zipcodes')
})
```

```text
zip:
    kind: Dimension
    field: student_name
    id_field: student_id
    singular: Student
    plural: Students
```

… is the same as

```text
shelf = Shelf({
'zip': Dimension(MyTable.student_name,
                 id_expression=MyTable.student_id,
                 singular='Student',
                 plural='Students')
                 })
```

Lookup is a dictionary that will change the value but not the id of a dimension.

```text
class_year:
    kind: Dimension
    field: class_year
    lookup:
        FR: Freshman
        SO: Sophomore
        JR: Junior
        SR: Senior
```

## Named Formats

Many formats are predefined and can be referred to by name.

These are the named formats that are currently supported:

| comma: | ‘,.0f’ |
| :--- | :--- |
| dollar: | ‘$,.0f’ |
| percent: | ‘.0%’ |
| comma1: | ‘,.1f’ |
| dollar1: | ‘,.1f’ |
| percent1: | ‘.1%’ |
| comma2: | ‘,.2f’ |
| dollar2: | ‘$,.2f’ |
| percent2: | ‘.2%’ |

In other words, this…

```text
sales:
kind: Metric
field: sales_dollars
format: dollar
```

… is the same as this

```text
sales:
kind: Metric
field: sales_dollars
format: '$,.0f'
```

## Icons

Ingredients may have [FontAwesome](https://fontawesome.com/v4.7.0/icons/) icons specified that fit the data concept well and add more personality to the data story. These icons will appear in filtering pills.

```text
sales:
kind: Metric
field: sales_dollars
format: dollar
icon: money
```

{% hint style="info" %}
Ingredients get/receive icons based on the specified format.
{% endhint %}

