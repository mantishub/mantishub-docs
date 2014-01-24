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
