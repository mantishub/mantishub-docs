==========================
Frequently Asked Questions
==========================

Is it possible to migrate my MantisBT instance to MantisHub?
------------------------------------------------------------

Yes, we provide consulting services to migrate your existing instance if it meets the following criteria:

- Uses MySQL as the backend database
- No code customization
- No dependency on plugins
- Is based on MantisBT v1.2.x or older (i.e. a stable release).

If you would like to migrate your instance contact MantisHub team with the following information:

- What MantisBT version are you currently running?
- Where is your MantisBT currently hosted?

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
Paid customers can contact support to get latest backup of their data.
The data will include the database dump and attachments.
