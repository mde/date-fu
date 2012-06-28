date-utils
==========

Utilities for working with JavaScript Dates

* * * * *

Some useful methods for dealing with dates, including:

-   `strftime` – formats dates based on a string
    input.
-   `add` – increments a date the desired number of
    units.
-   `diff` – gets the time difference between two
    dates.

### Syntax

strftime(dt, formatString);

### Parameters

dt <span class="dataType">(Object/Date or Number)</span> – The date to
be formatted, JS Date or numeric timestamp.

formatString <span class="dataType">(String)</span> – Indicates how the
date is to be formatted.

### Description

Formats a date or time according to a given format string – identical to
the strftime function found in many scripting languages such as Perl,
Ruby, or PHP.

### Examples

    var bd = new Date('12/27/1968');
    strftime(bd, 'My birthdate was %A, %B %e, %Y.');
    => 'My birthdate was Friday, December 27, 1968.'

    var dt = new Date('10/01/2112');
    strftime(dt, 'I found a guitar in %B of %Y.');
    => 'I found a guitar in October of 2112.'

add
---------------------

### Syntax

someHash.add(someKey, value);

### Parameters

dt <span class="dataType">(Object/Date or Number)</span> – The date to
be incremented/decremented.

interval <span class="dataType">(constant, see
dateParts)</span> – the unit (e.g., days, weeks,
hours, minutes) of time that the date is to be incremented/decremented.

count <span class="dataType">(Number)</span> – The number of the desired
units to increment/decrement the date.

### Description

Increments/decrements a date by some number of a specified unit of time
(e.g., adds three weeks, subtracts eight hours).

### Examples

    var dateParts = dateParts;
    // Add 10 years
    var bd = new Date('12/27/1968');
    bd = add(bd, dateParts.YEAR, 10);
    => Wed Dec 27 1978 00:00:00 GMT-0600 (CST)

    // Subtract 2 hours
    var dt = new Date(2112, 9, 1, 12, 45);
    dt = add(dt, dateParts.HOUR, -2);
    => Sat Oct 01 2112 10:45:00 GMT-0500 (CDT)

diff
----------------------

### Syntax

diff(dtA, dtB, interval);

### Parameters

dtA, dbB <span class="dataType">(Object/Date or Number)</span> – The
dates to be compared.

interval <span class="dataType">(constant, see
dateParts)</span> – the unit (e.g., days, weeks,
hours, minutes) of time to use when comparing the two dates.

### Description

Returns the time difference between two dates, measured in a specified
unit of time (e.g., how many days between, how many hours between, how
many weeks between).

### Formattting

The format string may include the following specifiers:

 * %a -- Abbreviated weekday name (ex. Thu)
 * %A -- Full weekday name (ex. Thursday)
 * %b -- Abbreviated month name (ex. Nov)
 * %B -- Full month name (ex. November)
 * %c -- Appropriate date and time representation (ex. Thu Nov 03 13:10:35 2005)
 * %C -- Century number (the year divided by 100 and truncated to an integer, range 00 to 99), single digits are preceded by zero (ex. 20)
 * %d -- Day of month (range 01 to 31), single digits are preceded by zero (ex. 03)
 * %D -- Date as %m/%d/%y (ex. 11/03/05)
 * %e -- Day of the month as a decimal number (range ' 1' to '31') -- a single digit is preceded by a space (ex. ' 3')
 * %F -- Same as %Y-%m-%d
 * %h -- Same as %b (ex. Nov)
 * %H -- Hour as a decimal number using a 24-hour clock (range 00 to 23), single digits are preceded by zero (ex. 13)
 * %I -- Hour as a decimal number using a 12-hour clock (range 01 to 12), single digits are preceded by zero (ex. 01)
 * %j -- Day of the year as a decimal number (range 001 to 366) -- zero-padded to three digits (ex. 307)
 * %k -- Hour as a decimal number using a 24-hour clock (range ' 0' to '23'), single digits are preceded by a space (ex. '13')
 * %l -- Hour as a decimal number using a 12-hour clock (range ' 1' to '12'), single digits are preceded by a space (ex. ' 1')
 * %m -- Month as a decimal number (range 01 to 12), single digits are preceded by zero (ex. 11)
 * %M -- Minute as a decimal number (range 00 to 59), single digits are preceded by zero (ex. 10)
 * %n -- Linefeed character ('\n')
 * %p -- Either 'AM' or 'PM' according to the given time value (ex. PM)
 * %r -- Appropriate time representation in 12-hour clock format with %p (ex. 01:10:35 PM)
 * %R -- Time as %H:%M (ex. 13:10)
 * %S -- Second as a decimal number (range 00 to 59), single digits are preceded by zero (ex. 35)
 * %t -- Tab character ('\t')
 * %T -- Time as %H:%M:%S (ex. 13:10:35)
 * %u -- Weekday as a decimal number (range 1 to 7), with 1 representing Monday (ex. 4)
 * %w -- Weekday as a decimal number (range 0 to 6), with 0 representing Sunday (ex. 4)
 * %x -- Appropriate date representation without the time (ex. 11/03/05)
 * %X -- Appropriate time representation without the date (ex. 01:10:35)
 * %y -- Year as a decimal number without a century (range 00 to 99), single digits are preceded by zero (ex. 05)
 * %Y -- Year as a decimal number including the century (ex. 2005)
 * %% -- A literal percent character (ex. %)

### Examples

    var dateParts = dateParts;

    // Number of months between these dates
    var dt1 = new Date('01/01/2112');
    var dt2 = new Date('10/01/2112');
    var diff = diff(dt1, dt2, dateParts.MONTH);
    => 9

    // Number of weekdays between these dates
    var dt1 = new Date('09/11/2007');
    var dt2 = new Date('09/28/2007');
    var diff = diff(dt1, dt2, dateParts.WEEKDAY);
    => 13


