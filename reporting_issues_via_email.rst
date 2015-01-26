==========================
Reporting Issues via Email
==========================

The goal of the feature is to provide the ability for users to email their issue reports which would then be automatically added to MantisHub.

This feature is in preview and is available to accounts on the Platinum plan.

Target Email Address
--------------------

- Email address for default project for the user account used as reporter ([instance]@mantishub.com).
- Email address per project (e.g. [instance+projectname]@mantishub.com.  The '+' must be used to separate the instance name and project name.
- For project name, replace non-alpha numeric characters with underscores.

Reporter Match
--------------

- The matching will happen based on the sender email address.  If a user with the same address exists, then such user account will be used as the reporter.
- If sender doesn't match, then user account named "Email" will be used, if it exists.  If it doesn't exist, then the message will be rejected.
- If "Email" account is used, then sender email address will be included in the issue additional information field.

Email to Issue Mapping
----------------------

- Sender maps to issue reporter or fallback to Email account.
- Subject maps to issue summary (title).
- Body maps to issue description (html is converted to text).
- Project is set based on project on the recipient email address, configured default project or reporter's default project.
- Default values used for fields not specified above.
- Embedded images and files are mapped to issue attachments.
- Attached files are mapped to issue attachments.

Spam Filtering
--------------

- Email messages that are marked as spam via the spam filter, will be rejected.  There will be no non-delivery notification for such messages.
- It is possible to reduce spam possibility by requiring a sender address match, hence, not having an account with name “Email”.  In such case, the spammer needs to figure out the sender and the destination addresses rather than just the destination.

Workflows
---------

- **Standard** - Emails will be delivered to project specific on the email address or fallback to the default project set for the reporter (whether the reporter is "Email" user or the sender account).
- **Incoming Project** - Create a project that would act as a landing place to all emails.  Then triage such emails and move them to the appropriate project or delete them.

Configuration
-------------

- **email_incoming_enabled** - Set to 1 to enable the feature (default) and 0 to disable it.
  - For example, go to Manage - Manage Configuration and add: All Users, All Projects, email_incoming_enabled, integer, 1
- **email_incoming_default_project** - If project name is not specified on the recipient email address, and this config has a value other than 0 (which is the default), then the issue is filed under the specified project id.  Otherwise, the default project for the reporter account is used.
  - The project ids can be retrieved from Manage - Manage Project - “project name” and then checking the id in the URL bar.
  - For example to set to project id 1, go to Manage - Manage Configuration and add: All Users, All Projects, email_incoming_default_project, integer, 1
- **email_incoming_issue_reported_message** - Template for message sent when an incoming email is reported
  successfully.  Supported parameters: {issue_id}.  For example, "Thanks for your email.  We've recorded the
  issue with reference number {issue_id}."
- **email_incoming_failed_message** - Template for messages sent when an incoming email is rejected.
  Supported parameters: {error}.  For example, "{error}".


