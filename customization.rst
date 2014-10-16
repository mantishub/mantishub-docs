=============
Customization
=============



--------------
User Interface
--------------

Replace MantisHub logo with your company logo?
----------------------------------------------
Administrators can replace MantisHub logo with their own company logo.
The logo must be in png format with size smaller than or equal to 50K.
The logo will be resized to have a height of no more than 80 pixels.
Go to Manage - Manage Configuration - Logo and upload your logo from there.
If the logo doesn't update right away, click the browser refresh button.

Enabling use of real names
--------------------------

You should be able to achieve that via the "Manage - Manage Configuration" page. You need to add the following settings: ::

	All Projects, All Users, show_user_realname_threshold, Integer, 0
	All Projects, All Users, show_realname, Integer, 1

-------------------
Email Notifications
-------------------

Receive notifications for my own actions
----------------------------------------
By default MantisHub excludes currently user from notifications due to their actions.
This behavior can be changed via the "Manage - Manage Configuration" page.
You need to add the following setting: ::

	All Projects, All Users, email_receive_own, Integer, 1

--------
Projects
--------

Enabling managers to create projects
------------------------------------

You should be able to achieve that via the "Manage - Manage Configuration" page. You need to add the following setting: ::

	All Projects, All Users, create_project_threshold, integer, 70

-----
Users
-----

Allow users to sign up
----------------------

Paid users can enable users to sign up to their MantisHub.
This can be done by emailing the request to support@mantishub.com.

Allow anonymous access
----------------------

Paid users can enable anonymous access to their MantisHub.
This can be done by emailing the request to support@mantishub.com.

---------------------------------------------------
Columns in View Issues, Csv Export and Excel Export
---------------------------------------------------

Administrators can customize the default columns for all users via: Manage - Manage Configuration - Manage Columns.

-----------------------------------
Statuses, Priorities and Severities
-----------------------------------

How to customize issue statuses?
--------------------------------

Paid users can customize issue statuses.
This can be done by emailing the request to support@mantishub.com.
Please include answers to the following questions:

- HTML color to use for it. - Use http://www.w3schools.com/tags/ref_colorpicker.asp for picking new colors and compare against the legend on the View Issues page to make sure the colors are not to close to other statuses.
- Status name in English and each other language you care about (e.g. ’tested’ for English). Choose from list of languages under "My Account - Preferences - Language".
- When changing status, there are three strings used - they are also needed in English + each language you care about. 
	- The title for the form requesting change of status - e.g. ‘Mark Issue as Tested’. 
	- The button on the form request change of status - e.g. ‘Tested’ 
	- The action description in the email notification - e.g. ‘The following issue has been TESTED.’.
- What is the order of the statuses?

How to customize issue priorities?
----------------------------------

Paid users can customize issue priorities.
This can be done by emailing the request to support@mantishub.com.
Please include answers to the following questions:

- Priority name in English and each other language you care about (e.g. ’urgent’ for English). Choose from list of languages under "My Account - Preferences - Language".
- What is the order of the priorities?  From lowest to highest.

How to customize issue severities?
----------------------------------

Paid users can customize issue severities.
This can be done by emailing the request to support@mantishub.com.
Please include answers to the following questions:

- Severity name in English and each other language you care about (e.g. ’blocking’ for English). Choose from list of languages under "My Account - Preferences - Language".
- What is the order of the severities?  From lowest to highest.

------
Fields
------

Enable 'due date' field
-----------------------

You should be able to achieve that via the "Manage - Manage Configuration" page. You need to add the following setting: ::

	All Projects, All Users, due_date_update_threshold, integer, 55
	All Projects, All Users, due_date_view_threshold, integer, 10
	All Projects, All Users, view_issues_page_columns, complex, array('selection', 'edit', 'priority', 'id', 'sponsorship_total', 'bugnotes_count', 'attachment_count', 'category_id', 'severity', 'status', 'last_updated', 'due_date', 'summary')


The 10 and 55 represent viewer and developer from the access levels table.
You can replace with whatever access levels that make sense for your requirement.

-------------
Custom Fields
-------------

Adding Custom Fields
--------------------

The process of adding custom fields includes defining the custom field and then linking it to the appropriate projects.
To create a custom field click "Manage - Manage Custom Fields" then enter field name, click "New Custom Field" and edit the custom field definition.
For custom field types that allow selection from a set of values use the '|' character to separate the different values.
Make sure to check the boxes specifying the pages on which the custom field should appear and is required.

The next step is to link the custom field to the appropriate project.
This can be done by click the custom field definition, scroll to bottom of page, then select the projects and click "Link Custom Fields".
The sequence number is used to determine the relative order of custom fields to each other.
Smaller sequence numbers are shown first.
It is also possible to link, unlink or re-order custom fields from project page (Manage - Manage Projects - click project name).

---------------------
Reference information
---------------------

Access Levels
-------------

====   ============
Code   Access Level
====   ============
10     viewer
25     reporter
40     updater
55     developer
70     manager
90     administrator
====   ============

Statuses
--------

====   ============
Code   Status
====   ============
10     new
20     feedback
30     acknowledged
40     confirmed
50     assigned
80     resolved
90     closed
====   ============
