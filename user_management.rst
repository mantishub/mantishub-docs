

===============
User Management
===============

Creating User Accounts
######################

In MantisBT, there is no limit on the number of user
accounts that can be created.  Typically, installations with thousands
of users tend to have a limited number of users that have access level
above REPORTER.

By default users with ADMINISTRATOR access level have access to create
new user accounts.  The steps to do that are:

- Click "Manage" on Main Menu.

- Click "Manage Users" (if not selected by default).

- Click "Create New Account" button just below the alphabet
  key.

- Enter user name, email address, global access level (more details about
  access levels later).  Other fields are optional.

- Click "Create Users".

Creating a user triggers the following actions:

- Creating a user in the database.

- If email notifications ($g_enable_email_notification) is
  set to ON, then the user will receive an email allowing them to
  activate their account and set their password.  Otherwise, the
  account will be created with a blank password.

- If email notifications ($g_enable_email_notification) is
  set to ON, users with access level about
  $g_notify_new_user_created_threshold_min will get a
  notification that a user account has been created.  Information
  about the user like user name and email address are provided.
  The IP of the user that created the account is also
  included.

When the 'Protected' flag is set on a user account, it indicates
that the account is a shared account (e.g. demo account) and hence users
logged using such account will not be allowed to change account
preferences and profile information.

The anonymous user account specified with the $g_anonymous_account
option will always be treated as a protected user account. When you are
creating the anonymous user account, the 'Protected' flag is essentially
ignored because the anonymous user is always treated as a protected
user.

Enabling/Disabling User Accounts
################################

The recommended way of retiring user accounts is to disable them.
Scenarios where this is useful is when a person leaves the team and it
is necessary to retire their account.

Once an account is disabled the following will be enforced:

- All currently active sessions for the account will be
  invalidated (i.e. automatically logged out).

- It will no longer be possible login using this account.

- No further email notifications will be sent to the account
  once it is disabled.

- The user account will not show anymore in lists like
  "assign to", "send reminder to", etc.

The disabling process is totally reversible.  Hence, the account
can be re-enabled and all the account history will remain intact.  For
example, the user will still have issues reported by them, assigned to
them, monitored by them, etc.

Deleting User Accounts
######################

Another way to retire user accounts is by deleting them.  This
approach is only recommended for accounts that have not been active
(i.e. haven't reported issues).  Once the account is deleted, any
issues or actions associated with such account, will be associated with
user123 (where 123 is the code of the account that was deleted).  Note
that associated issues or actions are not deleted.

As far as the underlying database, after the deletion of a user,
records with the user id as a foreign key will have a value that no
longer exists in the users table.  Hence, any tools that operate
directly on the database must take this into consideration.

By default administrators are the only users who can delete user
accounts.  They can delete accounts by clicking Manage, Manage Users,
locating the user to be deleted and opening it details page, then
clicking on the "Delete User" button which deletes the user.

Note that "Deleting Users" is not a reversible process.  Hence, if
it is required to re-add the user account, it is not possible to
recreate the user account so that it gets the same ID and hence retains
its history.  However, manually creating a record in the users table
with the same id, can possibly do that.  However, this approach is not
recommended or supported.

User Signup
###########

For open source and freeware projects, it is very common to setup
MantisBT so that users can signup for an account and get a REPORTER
access by default (configurable by the
$g_default_new_account_access_level configuration option).  The signup
process can be enabled / disabled using the $g_allow_signup
configuration option, which is enabled by default.

If user signup is enabled, then it is required that
$g_send_reset_password is ON as well, and the e-mail settings properly
configured
(see :ref:`Email Configuration <admin.config.email>`).

If email notifications ($g_enable_email_notification) is
set to ON, users with access level about
$g_notify_new_user_created_threshold_min will get a
notification that a user account has been created.  Information
about the user like user name, email address, IP address are included in
the email notification.

Forgot Password and Reset Password
##################################

It is pretty common for users to forget their password.  MantisBT
provides two ways to handle such scenario: "Forgot Password" and "Reset
Password".

"Forgot Password" is a self service scenario where users go to the
login page, figure out they don't remember their password, and then click
the "Lost your password?" link.  Users are then asked for their user
name and email address.  If correct, then they are sent an email with a
link which allows them to login to MantisBT and change their password.

"Reset Password" scenario is where a user reports to the
administrator that they are not able to login into MantisBT anymore.
This can be due to forgetting their password and possibly user name or
email address that they used when signing up.  The administrator then
goes to Manage, Manage Users, locates the user account and opens its
details.  Under the user account details, there is a "Reset Password"
button which the administrator can click to reset the password and
trigger an email to the user to allow them to get into MantisBT and set
their password.  In the case where email notifications are disabled,
resetting password will set the password to an empty string.

Changing Password
#################

Users are able to change their own passwords (unless their account
is "protected").  This can be done by clicking on "My Account", and then
typing the new password in the "Password" and "Confirm Password" fields,
then clicking "Update User".  Changing the password automatically
invalidates all logged in sessions and hence the user will be required
to re-login.  Invalidating existing sessions is very useful in the case
where a user going onto a computer, logs into MantisBT and leaves the
computer without logging out.  By changing the password from another
computer, the session on the original computer automatically becomes
invalidated.

Pruning User Accounts
#####################

The pruning function allows deleting of user accounts for accounts
that have been created more than a week ago, and they never logged in.
This is particularly useful for users who signed up with an invalid email
or with a typo in their email address address.

The account pruning can be done by administrators by going to
"Manage", "Manage Users", and clicking the "Prune Accounts" button
inside the "Never Logged In" box.

Authorization and Access Levels
###############################

MantisBT uses access levels to define what a user can do.  Each
user account has a global or default access level that is associated
with it.  This access level is used as the access level for such users
for all actions associated with public projects as well as actions that
are not related to a specific project.  Users with global access level
less than $g_private_project_threshold will not have access to private
projects by default.

The default access levels shipped with MantisBT out of the box are
VIEWER, REPORTER, UPDATER, DEVELOPER, MANAGER and ADMINISTRATOR.  Each
features has several configuration options associated with it and
identifies the required access level to do certain actions.  For
example, viewing an issue, reporting an issue, updating an issue, adding
a note, etc.

For example, in the case of reporting issues, the required access
level is configurable using the $g_report_bug_threshold configuration
option (which is defaulted to REPORTER).  So for a user to be able to
report an issue against a public project, the user must have a
project-specific or a global access level that is greater than or equal
to REPORTER.  However, in the case of reporting an issue against a
private project, the user must have project specific access level (that
is explicitly granted against the project) that is higher than REPORTER
or have a global access level that is higher than both
$g_private_project_threshold and $g_report_bug_threshold.

Note that project specific access levels override the global
access levels.  For example, a user may have REPORTER as the global
access level, but have a MANAGER access level to a specific project.  Or
a user may have MANAGER as the global access level by VIEWER access to
a specific project.  Access levels can be overridden for both public and
private projects.  However, overriding access level is not allowed for
users with global access ADMINISTRATOR.

Each feature typically has multiple access control configuration
options to defines what access level can do certain operations.  For
example, adding a note may require REPORTER access level, updating a
note my require DEVELOPER access level, unless the own was owned by the
same user and in this case REPORTER access level.  Such threshold
configuration options can be set to a single access level, which means
users with such threshold and above are authorized to do such action.
The other option is to specify an array of access level which indicates
that users with the explicitly specific thresholds are allowed to do
such actions.

It is also worth mentioning that the access levels are defined by
the $g_access_levels_enum_string configuration option, and it is
possible to customize such list.  The default value for the available
access levels is '10:viewer, 25:reporter, 40:updater, 55:developer,
70:manager, 90:administrator'.  The instructions about how to customize
the list of access levels will be covered in the customization section.

Auto Creation of Accounts on Login
##################################

In some cases MantisBT is setup in a way, where it allows users
that already exists in a directory or another application to be
automatically authenticated and added to MantisBT.  For example, a
company may setup their MantisBT installation in a way, where its staff
members that are already registered in their LDAP directory, should be
allowed to login into MantisBT with the same user name and password.
Another example, is where MantisBT is integrated into some content
management system, where it is desired to have a single registration and
single sign-on experience.  In such scenarios, once a user logs in for
the first time, a user account is automatically created for them,
although the password verification is still done against LDAP or the
main users repository.

User Preferences
################

Users can fine tune they way MantisBT interacts with them via
modifying their user preferences.  User preferences can only be managed
by users and are not available for the administrators to tweak.  The
administrators can only tweak the default value for such preferences.
However, once a user account is created, it is then the responsibility
of the user to manage their own preferences.  The user preferences
include the following:

- Default Project: A user can choose the default project
  that is selected when the user first logs in.  This can be a
  specific project or "All Projects".  For users that only work on
  one project, it would make sense to set such project as the
  default project (rather than "All Projects").  The active
  project is part of the filter applied on the issues listed in
  the "View Issues" page.  Also any newly reported issues will be
  associated with the active project.

- Refresh Delay: The refresh delay is used to specify the
  number of seconds between auto-refreshes of the View Issues
  page.

- Redirect Delay: The redirect delay is the number of
  seconds to wait after displaying flash messages like "Issue created
  successfully", and before the user gets redirected to the
  next page.

- Notes Sort Order: The preference relating to how notes
  should be ordered on an issue is viewed or in email
  notifications.  The ascending order is where notes are ordered
  so that ordered notes appear before newer notes, the descending
  order is the reverse.

- Email on New: If unticked, then email notifications
  relating to creation of a new issue would be disabled.  Note
  that the preference is only used to disabled notifications that
  as per the administrator's configuration, this user would have
  qualified to receive them.

- Email on Change of Handler: TODO - is this preference
  used?

- Email on Feedback: TODO - is this preference used?

- Email on Resolved: TODO

- Email on Closed: TODO

- Email on Reopened: TODO

- Email on Note Added: TODO

- Email on Status Change: TODO

- Email on Priority Change: TODO - is this preference used?

- Email Notes Limit: This preference can be used to limit
  the number of issue notes to view or to be included in an email
  notifications.  Specifying N here means that the latest N
  notes will be included.  The value 0 causes all notes to be
  included.

- Language: The preferred language of the user.  This
  language is used by the GUI and in email notifications.  Note
  that MantisBT uses UTF8 for encoding the data, and hence, the
  user can be interacting with MantisBT user interface in Chinese
  while logging issue data in German.

User Profiles
#############

A user profile describes an environment that the user uses to run
the software for which issues are being tracked.  The profile
information include "Platform", "Operating System", "OS Version", and
"Additional Description".  Each user has access to profiles that they
create (can be multiple), in addition to global ones that are shared
created by other users.  When reporting issues, users can elect to enter
information like platform, operating system, version manually, or they
can choose from the list of profiles that are already defined.

Global profiles are typically used by the administrator to define
a set of standard profiles that are typically used by the MantisBT
users.  This makes it easier for the users to use such profiles without
having to define create them.  The access level required for users to be
able to create global profiles is configured by the $g_manage_global_profile_threshold
configuration option and it is defaulted to MANAGER.

