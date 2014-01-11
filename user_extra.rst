
User Preferences
################

Users can fine tune they way MantisHub interacts with them via modifying their user preferences.  User preferences can only be managed by users and are not available for the administrators to tweak.
The administrators can only tweak the default value for such preferences.
However, once a user account is created, it is then the responsibility of the user to manage their own preferences.
The user preferences include the following:

- Default Project: A user can choose the default project that is selected when the user first logs in.
  This can be a specific project or "All Projects".
  For users that only work on one project, it would make sense to set such project as the
  default project (rather than "All Projects").
  The active project is part of the filter applied on the issues listed in the "View Issues" page.
  Also any newly reported issues will be associated with the active project.

- Refresh Delay: The refresh delay is used to specify the number of seconds between auto-refreshes of the View Issues page.

- Redirect Delay: The redirect delay is the number of seconds to wait after displaying flash messages like "Issue created successfully", and before the user gets redirected to the next page.

- Notes Sort Order: The preference relating to how notes should be ordered on an issue is viewed or in email notifications.
  The ascending order is where notes are ordered so that ordered notes appear before newer notes, the descending order is the reverse.

- Email on New: If unticked, then email notifications relating to creation of a new issue would be disabled.
  Note that the preference is only used to disabled notifications that as per the administrator's configuration, this user would have qualified to receive them.

- Email on Change of Handler: TODO - is this preference used?

- Email on Feedback: TODO - is this preference used?

- Email on Resolved: TODO

- Email on Closed: TODO

- Email on Reopened: TODO

- Email on Note Added: TODO

- Email on Status Change: TODO

- Email on Priority Change: TODO - is this preference used?

- Email Notes Limit: This preference can be used to limit the number of issue notes to view or to be included in an email notifications.
  Specifying N here means that the latest N notes will be included. 
  The value 0 causes all notes to be included.

- Language: The preferred language of the user.
  This language is used by the GUI and in email notifications.
  Note that MantisHub uses UTF8 for encoding the data, and hence, the user can be interacting with MantisHub user interface in Chinese while logging issue data in German.

User Profiles
#############

A user profile describes an environment that the user uses to run the software for which issues are being tracked.
The profile information include "Platform", "Operating System", "OS Version", and "Additional Description".
Each user has access to profiles that they create (can be multiple), in addition to global ones that are shared created by other users.
When reporting issues, users can elect to enter information like platform, operating system, version manually, or they can choose from the list of profiles that are already defined.

Global profiles are typically used by the administrator to define a set of standard profiles that are typically used by the MantisHub users.
This makes it easier for the users to use such profiles without having to define create them.
The access level required for users to be able to create global profiles is configured by the $g_manage_global_profile_threshold configuration option and it is defaulted to MANAGER.
