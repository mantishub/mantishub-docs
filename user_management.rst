===============
User Management
===============

Creating User Accounts
######################

Administrators have access to create new user accounts.  The steps to do that are:

- Click "Manage" on Main Menu.
- Click "Manage Users" (if not selected by default).
- Click "Create New Account" button just below the alphabet key.
- Enter user name, email address, global access level (more details about access levels later).  Other fields are optional.
- Click "Create Users" button.

Creating a user triggers the following actions:

- Creating a user in the database.

- An email notification is sent to the created user enabling them to activate their account and set their password.

- Administrators will receive a notification that a new user has been created.
  Information about the user like user name and email address are provided.
  The IP of the user that created the account is also included.

When the 'Protected' flag is set on a user account, it indicates that the account is a shared account and hence users logged using such account will not be allowed to change account preferences and profile information.

Disabling User Accounts
#######################

The recommended way of retiring user accounts is to disable them.
Scenarios where this is useful is when a person leaves the team and it is necessary to retire their account.

Once an account is disabled the following will be enforced:

- All currently active sessions for the account will be invalidated (i.e. automatically logged out).
- It will no longer be possible login using this account.
- No further email notifications will be sent to the account once it is disabled.
- The user account will not show anymore in lists like "assign to", "send reminder to", etc.

The disabling process is totally reversible.  Hence, the account can be re-enabled and all the account history will remain intact.
For example, the user will still have issues reported by them, assigned to them, monitored by them, etc.

Deleting User Accounts
######################

Another way to retire user accounts is by deleting them.
This approach is only recommended for accounts that have not been active (i.e. haven't reported issues).
Once the account is deleted, any issues or actions associated with such account, will be associated with user123 (where 123 is the code of the account that was deleted).
Note that associated issues or actions are not deleted.

As far as the underlying database, after the deletion of a user, records with the user id as a foreign key will have a value that no longer exists in the users table.
Hence, any tools that operate directly on the database must take this into consideration.

By default administrators are the only users who can delete user accounts.
They can delete accounts by clicking Manage, Manage Users, locating the user to be deleted and opening it details page, then clicking on the "Delete User" button which deletes the user.

Note that "Deleting Users" is not a reversible process.
Hence, if it is required to re-add the user account, it is not possible to recreate the user account so that it gets the same ID and hence retains its history.
However, manually creating a record in the users table with the same id, can possibly do that.
However, this approach is not recommended or supported.

User Signup
###########

For open source and freeware projects, it is very common to setup MantisHub so that users can signup for an account and get REPORTER access.
The signup process is disabled by default and can be enabled by contacting the MantisHub support team.

When users signup, administrators get a notification with the details of the user that signed up.
Information about the user like user name, email address, IP address are included in the email notification.

Anonymous Access
################

MantisHub supports enabling read-only access for anonymous users.
This model is useful to enable users to browse your issues without having to create an account first.
However, if users are going to report issues or comment on issues, they are required to have a reporter account.
Anonymous access also enables search engines to index your MantisHub issues.

To enable anonymous access, users should create an account named 'anonymous'.
The account should be granted VIEWER access level.
The account also be given access to selected private projects, as appropriate.
Once the anonymous account is setup, notify MantisHub support and they will enable it such access for you.

It is important other not to grant anonymous access REPORTER access to avoid spam.
Having registered users enabled your development team to follow up with such users on issues or notes that they submit on your MantisHub.

Forgot and Reset Password
#########################

It is pretty common for users to forget their password.
MantisHub provides two ways to handle such scenario: "Forgot Password" and "Reset Password".

"Forgot Password" is a self service scenario where users go to the login page, figure out they don't remember their password, and then click the "Lost your password?" link.
Users are then asked for their user name and email address.
If correct, they are sent an email with a link which allows them to login to MantisHub and change their password.

"Reset Password" scenario is where a user reports to the administrator that they are not able to login into MantisHub anymore.
This can be due to forgetting their password and possibly user name or email address that they used when signing up.
The administrator then goes to "Manage", "Manage Users", locates the user account and opens its details.
Under the user account details, there is a "Reset Password" button which the administrator can click to reset the password and trigger an email to the user to allow them to get into MantisHub and set
their password.

Changing Password
#################

Users are able to change their own passwords (unless their account is "protected").
This can be done by clicking on "My Account", and then typing the new password in the "Password" and "Confirm Password" fields, then clicking "Update User".

Changing the password automatically invalidates all logged in sessions and hence the user will be required to re-login.
Invalidating existing sessions is very useful in the case where a user going onto a computer, logs into MantisHub and leaves the computer without logging out.
By changing the password from another computer, the session on the original computer automatically becomes invalidated.

Pruning User Accounts
#####################

Pruning user accounts allows deleting of user accounts for accounts that have been created more than a week ago, but never logged in.

This is particularly useful for users who signed up with an invalid email or with a typo in their email address address.

The account pruning can be done by administrators by going to "Manage", "Manage Users", and clicking the "Prune Accounts" button inside the "Never Logged In" box.

Authorization and Access Levels
###############################

MantisHub uses access levels to define what a user can do.
Each user account has a global or default access level that is associated with it.
This access level is used as the access level for such users for all actions associated with public projects as well as actions that are not related to a specific project.
Users that are not administrators, will not have access to private projects unless added explicitly to those projects.
The users access to a private project can be lower or higher than their global access level.

Following are the access levels in MantisHub and their typical usage.
Note that each level has all the priviledges of the ones before it.

- VIEWER - login and view issues.
- REPORTER - report issues and comments on issues.
- UPDATER - a user who can update issues.
- DEVELOPER - a team member who is able to view private issues, take ownership of issues and view reports.
- MANAGER - ability to manage a project including project details, who has access to it, categories, versions, and custom fields.
- ADMINISTRATOR - all administration tasks and communication with MantisHub support team.
