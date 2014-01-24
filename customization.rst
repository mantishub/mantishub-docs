=============
Customization
=============



--------------
User Interface
--------------

Replace MantisHub logo with your company logo?
----------------------------------------------
Paying customers can replace MantisHub logo with their own company logo by emailing a png version of their logo to support@mantishub.com along with the url to their instance.
Our support staff would promptly apply the change.

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

