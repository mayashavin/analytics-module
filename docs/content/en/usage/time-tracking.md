---
title: User timings tracking
description: How to track and measure user interactive time in GA
position: 7
category: Usage
---

This module injects `$ga` instance globally. You can access the instance anywhere using `this.$ga` (within a component), or `context.$ga` (for plugins, `asyncData`, `fetch`, `nuxtServerInit` ,and middleware)

## `time()`

The received parameters can be:

* Event `Object` contains:
  * `timingCategory` - for categorizing all user timing variables into logical groups
    * Type: `String`
    * `required`
  * `timingVar` - identify the variable being recorded ('load' for instance)
    * Type: `String`
    * `required`
  * `timingValue` - number of milliseconds in elapsed time to report
    * Type: `Number`
    * `required`
  * `timingLabel` - used to add flexibility in visualizing user timings in the reports
    * Type: `String`
  
```js
this.$ga.time({
  timingCategory: 'category',
  timingVar: 'variable',
  timingValue: 123,
  timingLabel: 'label'
})
```

Or the Event's information can be spread directly as separate arguments, in the exact order

```js
event(timingCategory, timingVar, timingValue, timingLabel)
```

For example:

```js
this.$ga.time('category', 'variable', 123, 'label')
```
