# CalendarEvent

This library will help you in creating calendar events locally to the device & even delete those evnts that was created using this.


## Dependency

Add this in your root build.gradle file (not your module build.gradle file):

```
allprojects {
    repositories {
        maven { url "https://www.jitpack.io" }
    }
}

buildscript {
    repositories {
        maven { url "https://www.jitpack.io" }
    }
}
```

Then, add the library to your module build.gradle

```
dependencies {
    implementation 'com.github.kunal-wadhwa:CalendarEvents:latest.version'
}
```

## Features

- Create Caledar events will be synced with your local device
- Set reminder for that event. Time for reminder is also Dynamic.
- Can add almost all the event's information
  - Title
  - Description
  - Place
  - Start date
  - End date
  - Reminder Required or not (If yes then the time for the reminder)
  - is Alaram required or not
- Delete that event that was created with the help of this library.

## Usage

### Make sure to provide the calendar write & read permission to your application before using it.

```
    <uses-permission android:name="android.permission.READ_CALENDAR" />
    <uses-permission android:name="android.permission.WRITE_CALENDAR" />
```

There are majorly two methdos
 - createCalendarEvent
```
fun createCalendarEvent(
            context: Context?, title: String?,
            description: String?, place: String?, status: Int?, startDate: Calendar?,
            endDate: Calendar?, needsReminder: Boolean?, reminderBefore:Int?,
            allDay: Boolean?, hasAlarm: Boolean?
        ): Long
```

This method help in creating the event as per the parameters & will return the eventId(Long) for the event that is being created.
You can store it somewhere safe this will help you if in future if you want to delete that particular event.

- deleteCalendarEvent
```
 fun deleteCalendarEvent(context: Context?, eventId: Int)
```
This method will help in deleting that particular event for which the eventId is passed.

If eventId is -1 -> this means that event is not being created successfully.

