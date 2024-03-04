---
layout: default
title: Mobile Apps
nav_order: 4
---

# Mobile App Assignments
{: .no_toc }

## Table of Contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## UVA Bucket List (Android)

### Getting Started: GitHub and Android Studio

First, head to GitHub to create your repo in our classroom GitHub organization by going here: [https://classroom.github.com/a/Lt3SEAIR](https://classroom.github.com/a/Lt3SEAIR).

Android Studio has GitHub integration built in, so you can clone this repo (which includes a starter "hello world" app) and build your app out in that proctect.



### Requirements and Specifications

For your Android Individual App, you are going to build a simple UVA Bucket List app.  Users will be able to open this app and add items to their bucket list of things that they want to do before graduation.  Each item will have a name, a due date, and a way to record whether it has been completed or not.  This app should use persistence via a private SQLite database to store information, so that any changes to the bucket list are stored on the device. For this persistence, I highly recommend using Room as we showed in class, but you are welcome to use a SQLite database however you wish to store data.

Your app will revolve around one data type. You should have a **data class BucketItem** in your project which stores the following information.

__BucketItem__
1) A String with the name of the bucket list item ("Eat at Now & Zen")
2) A due date for when the item is expected to be complete by (May 1, 2024)
3) A Boolean for stating whether the item is completed (**true**) or not (**false**)
4) A **nullable** completed Date, which is null if the item is not completed, or includes the date the item was marked as done


Your app must meet the following requirements.  Beyond these requirements, you can customize your app as you see fit.

The app must have these three activity screens - a list screen, a create new item screen, and an item information screen. 
All three must be implemented as separate Activities, with Intents used to communicate to/start other activities.
More detailed information about each activity is found below.

__List Activity__

1. When the app starts up, the list screen should be the first one displayed.
2. This screen will display the bucket list items as a list.
3. Each bucket list item must include: 
   1. the name of the item, 
   2. the due date, 
   3. a checkbox (or something similar) for a user to click to check off the item as being done. If the item is completed, the checkbox should be checked. If not, the checkbox should be empty.
   4. An edit button that lets me edit the item - You are recommended to use the Android pencil icon for this button, but that is only a recommendation.
4. There must be a button somewhere on the screen (ideally top or bottom) to go to the **Add Item Activity**.
5. The items in the list should be in order by, first, whether they are completed, and second, from the earliest **due date** to latest.
   1.  **completed** items should be at the bottom of the list, below all un-completed items.
   2. However, both completed and uncompleted items should be sorted by due date.
6. Tapping on the edit button (not on the checkbox) should bring up an Edit Item activity (see that Activity for more info).
7. Tapping on the checkbox next to an item should flip it's done / not done status.
   1. Note that whenever you tap the checkbox marking an item completed, that BucketItem's completion date should be updated to the current date
   2. It should also move the item to the "completed" part of the list
8. Tapping on the floating action button should bring up the Add Item activity (see that Activity for more info).

__Add Item Activity__

1. The screen should have editable fields for each of the parts of a bucket list item.
   1. Text field for the name
   2. Datepicker for the due date
   3. Checkbox for the "is completed" feature
   4. There should **not** be a "date completed" DatePicker, since the bucket item's "finished date" should be based on when the Checkbox is pressed
2. There should be a **save** button at the bottom of the screen which saves all changes and returns to the List Activity
   1. These changes should be reflected in the List Activity, and should also be persisted to the database
3. There should be a **cancel** button at the bottom of the screen. If this is pressed, this should return to the List Activity, but with no changes persisted (i.e., if the name or data were changed, but then the user hits cancel, then nothing should change neither in the List Activity nor in the database).

__Item Info Activity__

1. The screen should look the same as the Add Item activity, but with the information from the bucket list item whose edit button you tapped pre-populated with the information about that bucket item AND it should also have the date that the item was completed.
2. Any changes made here should be reflected back in the original item in the List Activity, and in the database
3. You should have the same "Save" and "Cancel" buttons as the add item activity.

__Style Requirement__

1. You must make *some* meaningful style changes in the Theme.kt file, including color them changes, text changes, etc. This don't need to be substantial, just something to show you have a basic understanding of the Theme.kt file.


### Submission and Grading

__Submission__

For the app itself, you do not need to do any manual submission.  We will grade the latest version in your GitHub repo.

For the report described below, please submit the required information into the associated assignment in Gradescope.

* 10 XP: App can launch properly into the List Activity
* 15 XP: Tapping on the Add Item button launches the Add New Item activity
* 20 XP: A new item is put into the list in the correct location after saving
* 10 XP: Tapping on the checkbox registers the item as complete and it moves to the bottom of the list
* 10 XP: Tapping on the edit button for an item opens the Edit Item activity
* 15 XP: The Edit Item activity is pre-populated with all appropriate data
* 10 XP: Changes Saved in the Edit Item activity are properly reflected back in the list
* 10 XP: The save and edit buttons work properly on both the Add and Edit screen
* 5 XP: App does not crash on rotate (you do not need to create a "landscape" layout, just your app shouldn't crash)
* 15 XP: Design / Style / Appearance / Usability
* 20 XP: Data persistence
* 10 XP: Answering questions on Gradescope when submitting

__Project Report__

Please answer the questions on the _Android UVA Bucket List_ assignment in Gradescope _and_ put this information into your `README` file in GitHub:

* Your name and UVA computing ID
* Any special features about your app we should know about
* Lessons learned from building this Android app (a paragraph at least)

__Late Policy__

Changes made to the GitHub repo after the due date and time will incur the following penalties:
* -15 XP up to 1 day late
* -30 XP up to 2 days late
* -60 XP up to 3 days late
* -120 XP up to 4 days late

### Tips
{: .no_toc }

1. Note that a "Bucket List" is a fairly simply to a to-do list CRUD app (Create, Read, Update, Delete).  
2. Consider that when you are looking for tutorials.
3. If you use code from elsewhere, it MUST be cited.  Also, wholesale using the "solution" from a tutorial you find that's "close enough" in your opinion is not going to earn any XP.


## UVA Bus Lines (Flutter)

Due Friday, March 29, 2024

### Summary

Build an app to allow users to see bus route maps, as well as their own current location. This app
must be built as a Flutter project which includes Android and iOS (but will only be graded on Android).

Gradescope link: https://classroom.github.com/a/0XLCoc9s

### Data Source

You will need to use a web API to ingest data to show: https://www.cs.virginia.edu/~pm8fc/busses/busses.json 


Be aware that you should **dynamically** read in this data at startup (no API key required), do not "hard code" 
the data on this page, or store it in a local database. However, you can limit to only reading *at* startup (i.e., don't worry about changes *while* the app is running). This data *will* be changed when we are grading!

### Map API

For this app, you will need to use a Map View to show BusRoutes as well as the current user location. We will *not*
be explicitly covering map apis in class, so it is intended for you to "learn by doing." The easiest approach is to use
either Google Maps API or OpenStreetMaps API (Apple Maps may not be used due to their device exclusivity).

This app *will* require users granting permission for location via GPS. 

Here are helpful links to get started. Be aware you should *only* pick one of these two for your app.

Google Maps: https://pub.dev/packages/google_maps_flutter 

Open Street Maps: https://pub.dev/packages/flutter_osm_plugin 

Be aware that Google's API keys require a credit card. However, you should not come close to actually being charged over
the course of this assignment.

You will also need an API key to use these. However, this API key **should not be pushed** - when grading, we will use
our own API keys. All API keys should be stored in your project in a file **api\api_keys.json** in the following format:

```json
{
   "MAPS_KEY": "your-api-key-goes-here"
}
```

Please make sure you use the above format **exactly** and keep the "MAPS_KEY" as your API key (regardless whichever service you use),
as this is how we will plug in our own API key to test your app.

### Platform Requirements

This assignment will be graded specifically on an Android emulator, so ensure your assignment works on Android. However,
you should still setup permissions for iOS for location and API usage.

### The App Interface

#### List View

On start-up, you should see a list of Bus Line names (such as "Red Line", "Blue Line", etc.) that are pulled from the above
.json file. Each of these names, when clicked, should pull up a Map View of those routes on the Map page. Additionally,
each route should have a **favorite button** next to it that is initially unselected. This button will mark that particular
busline as a favorite. **You must persist which routes are marked favorite** such that closing and reopening the app shows the same routes as favorited (You can use a SQLite database or shared preferences, whichever you prefer).

The list should be sorted **favorites first**, and then alphabetically. So if the routes are Apple, Banana, Carrot, Durian, and I favorite
Banana and Durian, my list should be in order:

* Banana  
* Durian  
* Apple  
* Carrot  

You only need to list the bus line names, but the name should be displayed using that route's "text_color" from the JSON.

#### Map View

When you click on a bus line, it should take you to the map view. The map view should show all the stops along the selected
line as pins on the map (you should *not* try to connect these pins with a line or driving directions, as that can start
to eat into your API "free limit"). 

The map should be initially bounded by the "bounds" part of that line's JSON for instance, the 29 North Connect Line should be
bound by: 

* 38.031599,  (southern boundary)
* -78.508578, (western boundary)
* 38.130205, (northern boundary)
* -78.436039 (eastern boundary)

From there, the map should support controls such as sliding to move the map, pinching/spreading for zooming in and out. Note that many pre-built map widgets already implement this behavior.

Additionally, the user's location should be visible on the map (unless the user's location is outside of the current map boundary) via their GPS coordinates for testing purposes on our emulator, I recommend setting the device's GPS coordinates to: 38.0316° N, 78.5108° W, which is Rice Hall.

Each Pin, when clicked/tapped, should show the name of the Bus Stop.

From the map view, hitting the "back button" should take you back to the List View

#### Grading

The App is worth 150XP

List View  (70XP)
- The app should start up on a list view of all buslines from the API by name (15 XP)  
- The names of the bus-line should be in the color specified from the web-service (5 XP)  
- The app should ask the user for GPS permission on the *first* startup - for grading purposes, you can assume we as the users will accept this permission. (10 XP)  
- Each bus line in the list view should have a favorite button that bus line as favorite, where the button should communicate whether the item is already favorited. This could be something like using a hollow-star if not-favorited, and a filled-in star in favorited. (10 XP)  
- Favoriting a bus line must be persistent - that is, if I favorite a line, close the app, then re-open the app, that line must still be favorited. (10 XP)  
- Favorite bus lines must be sorted before unfavorite buslines, and then by alphabetical order. (10 XP)  
- The sorting should dynamically update whenever a busline is favorite/unfavorited (10 XP)  

Map View  (70XP)
- Clicking on a busline should open a map view. (10 XP)  
- Hitting the back button in the map view takes you back to the list view (10 XP)  
- The map should be initially bounded from the data in the JSON (10 XP)  
- All bus stops on the selected route, and *only* the stops on the selected route, should be visible as pins (10XP)  
- Each pin, when tapped, shows a label contain that Stop's name (10 XP)  
- The map should be "moveable" and "zoomable" (10 XP)  
- The users GPS location should be shown, assuming it is within the map's boundaries (10 XP)  

In addition, when submitting on Gradescope, there will be on question to answer for 10XP

