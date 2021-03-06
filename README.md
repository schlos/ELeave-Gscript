# Introduction

A tweak to the tutorial found at http://info.groveis.com/blog/bid/152618/Tutorial-Build-a-Leave-Request-Management-System-with-Google-Apps
Supports half day leave requests, and an approval interim.

# Requirements

* Google account
* 2 Google calendars (one for requests and one for approved)
* 1 Google spreadsheet and form

# Instructions

Look through the code, replace the following (use find tool)

XXXX - email address to send requests to  
YYYY - Calendar with confirmed leave  
ZZZZ - Calendar with leave requests  
WWWW - Spreadsheet ID (go to the spreadsheet, choose share, in the url, there should be ...key=WWWW&...  
VVVV - The column number to track status (Assing an unused column to track status A=1, B=2, etc)  

* Follow the instructions from the website to create the form (and the spreadsheet). Do not copy the script as we will be replacing it with this version.
* Create two additional fields called 'Start Date Type' and 'End Date Type'. The options for those are "Full Day", "Half Day AM" and "Half Day PM". Please note that all entries are case Sensitive.
* Create a script for the spreadsheet, copy and paste the code from code.gs
* Create a new script (file-> new-> script). Copy and paste the code form approval.gs
* Set trigger for code.gs such that it runs when form is submitted.
* Publish the app for approval.gs

# Usage

Publicise the link for the form. Check email to approve or reject. There is the temporary calendar so that it is easy to overlay both calendar to see who has taken leave and when. Open the spreadsheet to see an overview of the leave requests and status.

# Future TODO 

* Get user name and email address automatically, after restricting the access to this form internally. Can be done by something like `var email = Session.getEffectiveUser().getEmail();`
* Some form of tracking number of leaves taken.
* Nicer response after approval/declination.