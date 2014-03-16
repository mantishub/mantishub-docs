==========================
Frequently Asked Questions
==========================

Is it possible to migrate my MantisBT instance to MantisHub?
------------------------------------------------------------

Yes, see :ref:`migrations` for more details.

How can I access MantisHub issues from my tools?
------------------------------------------------

MantisHub provides a SOAP based webservice APIs that allows automation against MantisHub data.

The WSDL definition can be found at

	https://mantishub.mantishub.com/api/soap/mantisconnect.php?wsdl

The web service end point for instance 'foo' will be:

	https://foo.mantishub.com/api/soap/mantisconnect.php

There is also .NET client library available through http://www.futureware.biz/mantisconnect/

How do I get support?
---------------------

MantisHub provides support for trial and paid customers.
Contact MantisHub team via the in-app messaging using the "?" box on the bottom right of the screen when logged in as administrator.
You can also email us at support@mantishub.com from your administrator's email account.

How do I get my data?
---------------------

MantisHub performs daily backups of all free and paid MantisHub instances.
Customers can also download backups on demand via MantisHub interface.
Login as an administrator and go to Manage - Backup, request a backup, and download it.
The backup will include mysql database dump, configuration files, and attachments.

How do I add payment method?
----------------------------

All you need to do is setup your payment method in your account. After the 30-day trail is over, you will be automatically charged on a monthly basis. To do that

- Go to MantisHub.com and click on "Log in" button in the navbar or browse directly to https://accounts.mantishub.com/.
- Click on "Add payment method" and complete the form.

How to create a project?
------------------------

To start reporting issues, you need to create a project first.
This can be done as follows:

- Login as an administrator - If there are no project created yet, MantisHub will redirect to the create project page.
- If not redirected, navigate to project creation page by clicking on "Manage - Manage Projects" and click on "Create New Project" button next to the "Projects" title.
