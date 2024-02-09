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