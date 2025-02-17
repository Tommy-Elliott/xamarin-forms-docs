---
title: RecurrencePatternHelper
page_title: RecurrencePatternHelper
position: 3
slug: calendar-recurrence-recurrencepatternhelper
---

# RecurrencePatternHelper

When working with saving [recurrence patterns]({%slug calendar-recurrence-recurrencepattern%}), the RadCalendar's API provides he __RecurrencePatternHelper__ class, which comes from the *Telerik.XamarinForms.Input* namespace. The helper provides two main functions - turning a recurrence pattern into a nicely serialized string for storage and producing a recurrence pattern when you provide that string back to it.

The purpose of this tutorial is to show you how to:

* [Serialize](#serialize-a-recurrencepattern-to-string) a recurrence pattern to string.

* [Deserialize](#deserialize-a-recurrencepattern-from-string) a recurrence pattern from string.

## Serialize a RecurrencePattern to String

When you want to turn (serialize) a recurrence pattern into a string, then you need to use the __RecurrencePatternHelper__'s __RecurrencePatternToString()__ static method. The method accepts one argument - the pattern that must be serialized and returns the result string.

For example, consider the following __RecurrencePattern__ declaration:

```C#
var pattern = new RecurrencePattern()
{
	Frequency = RecurrenceFrequency.Daily,
	DaysOfWeekMask = RecurrenceDays.WeekDays,
	Interval = 3,
	MaxOccurrences = 10
};
```
A new daily recurrence pattern is created that occurs only in the week days. The interval between each occurrence is three days. The pattern has a limit of ten occurrences.

The next code snippet demonstrates you how to use the __RecurrencePatternToString()__ static method.    
  
```C#
var serializedPattern = RecurrencePatternHelper.RecurrencePatternToString(pattern);
```

After executing the above example the result string will be: __FREQ=DAILY;COUNT=10;INTERVAL=3;BYDAY=MO,TU,WE,TH,FR__.

## Deserialize a RecurrencePattern from String

When you want to produce (deserialize) a recurrence pattern from a string, then you need to use the __RecurrencePatternHelper__'s __TryParseRecurrencePattern__ static method. The method accepts two arguments:        

* The source string - the string which the recurrence pattern will be parsed from.

* The second parameter is an __out__ parameter. This is the parsed pattern.

Consider the serialized string from the previous example: __FREQ=DAILY;COUNT=10;INTERVAL=3;BYDAY=MO,TU,WE,TH,FR__. If you want to produce a recurrence pattern from that string, invoke the __TryParseRecurrencePattern__ method like in the example below.

```C#
var serializedPattern = "FREQ=DAILY;COUNT=10;INTERVAL=3;BYDAY=MO,TU,WE,TH,FR";
RecurrencePattern pattern;
RecurrencePatternHelper.TryParseRecurrencePattern(serializedPattern, out pattern);
```

The result will be a new daily recurrence pattern that occurs only in the week days. The interval between each occurrence is three days. The pattern has a limit of ten occurrences.

## See Also

* [Appointments]({%slug calendar-appointments%})
* [Recurrence Overview]({%slug calendar-recurrence-overview %})
