# Date = 2 April 2025
# PYTHON LIBRARIES
Today, I focused on understanding how to work with dates and times in Python using the datetime module. Since stock prices are time-series data therefore handling and manipulating dates is essential for building effective time-based predictions.

---

# Introduction to Datetime
The datetime module in Python is part of the standard library and provides a set of classes to work with dates, times and time intervals. It allows you to perform tasks such as:
1. Getting the current date and time.
2. Formatting dates and times.
3. Performing arithmetic on dates (e.g., adding days).
4. Parsing and converting between strings and datetime objects.

---

##  Several Key Classses:

1. date: For handling dates (year, month, day).
2. time: For handling times (hour, minute, second).
3. datetime: For handling both date and time.
4. timedelta: For representing the difference between two dates or times.
5. tzinfo: For dealing with time zones.

---

## What is Datetime?
Python Datetime could be a module that permits for the control of datetime objects. It contains capacities and classes for working with dates, times, and timezones. It can be utilized to change over strings to datetime objects, compare dates and times, and control the yield of dates and times in different groups. Python Datetime too gives tools for working with timezones, performing arithmetic operations with dates, and making calendars. 

---

## How to Use Date and Datetime Class?

The datetime module of Python offers various useful classes for effortlessly manipulating and processing dates and times. This module contains classes that can represent dates and times in a datetime object, allowing Python programmers to easily extract components of dates such as years, months, days, hours, minutes, and seconds. The datetime module additionally allows for simple date arithmetic and formatting date strings into standard formats. By utilizing the "datetime" module Python developers can efficiently handle date and time information in their programs without having to manually parse and calculate dates and times. The datetime module greatly simplifies the process of working with dates and times in Python applications.

---

## Working of DateTime:

1. Creating datetime objects: You can create a date or time object using the datetime.date() or datetime.time() methods respectively.

2. Manipulating datetime objects: You can add or subtract time intervals using the timedelta class.

3. Formatting and parsing: Use strftime() to format dates into strings and strptime() to parse strings into datetime objects.

---

## Classes of DateTime Python Module

1. The *date* data type stores calendar date information, including the year, month and day. It allows you to represent a specific date on the calendar.

2. The *time* data type stores the time of day including the hour, minute, second and microsecond. It allows you to represent a specific point in time each day.

3. The *datetime* data type combines the date and time data types to store both calendar date and time of day information together. It allows you to represent a full timestamp, specifying both when something happened and what day it occurred on.

4. The *timedelta* data type is used to compute the difference between two dates, times or datetimes. It allows you to calculate the amount of time between two points in time so you can determine how much time has passed or how much time remains until a future date.

5. The *tzinfo* data type is used to store timezone information. It allows you to specify the timezone for a particular date, time or datetime value so you know the local time represented and can correctly handle daylight saving time and other timezone-related adjustments.

---


## One Simple program for Scikit Learn Loading Dataset

```python

from sklearn import datasets
# Load data
iris= datasets.load_iris()
# Print shape of data to confirm data is loaded
print(iris.data.shape)

```

## One program for DateTime Python Library

```python

# Import the datetime module
import datetime

# 1. Get the current date and time
now = datetime.datetime.now()
print("Current Date and Time:", now)

# 2. Extract specific parts of the datetime (year, month, day, hour, minute, second)
print("Year:", now.year)
print("Month:", now.month)
print("Day:", now.day)
print("Hour:", now.hour)
print("Minute:", now.minute)

# 3. Add 7 days to the current date using timedelta
next_week = now + datetime.timedelta(days=7)
print("Date After 7 Days:", next_week)

# 4. Convert a string to a datetime object (parsing)
date_string = "2023-10-05 14:45"
date_obj = datetime.datetime.strptime(date_string, "%Y-%m-%d %H:%M")
print("Parsed Date:", date_obj)

# 5. Format datetime into a string (using strftime)
formatted_date = now.strftime("%A, %B %d, %Y %I:%M %p")
print("Formatted Date:", formatted_date)


```

## Today's Learning Summary:
Today, I learned about Python's datetime module which provides tools for working with dates, times and time intervals. This module includes several key classes such as date, time, datetime, timedelta and tzinfo allowing you to easily perform tasks like getting the current date and time, formatting, parsing date strings and performing arithmetic on dates (e.g. adding days). I explored how to create and manipulate datetime objects, extract specific components (like year, month, day etc.) and format dates into readable strings. Additionally, I saw an example of how to load a dataset using scikit-learn and handle datetime operations effectively in Python.