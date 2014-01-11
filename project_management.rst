==================
Project Management
==================

Changelog
#########

MantisHub doesn't just track the status of issues, it also relates issues to versions.
Each project can have several versions, which are marked with attributes like released and obsolete.
Users typically report issues against released issues and developers typically fix issues in not released versions.
With every new release comes question like: what's new? what has been fixed? Customers wonder if the new release is of interest to them and whether they should take an upgrade.
Well, the change log is specifically tailored to answer these kind of questions.

In order for an issue to show up in the change log, it has to satisfy certain criteria.
The criteria is that the issue has to be resolved with a 'fixed' resolution and has to have the 'fixed in version' field set.
Note that it is possible to set the 'fixed in version' for multiple issues using the 'Update Fixed in Version' group action on the "View Issues" page (just below the issues list).
This option is only available when the selected project is not 'All Projects'.
Once a version is marked as obsolete, it is now longer included in the change log.

Roadmap
#######

One of the very important scenarios in project management is where the project managers (or team leads) triage the issues to set their priorities, target version, and possibly assign the issues to specific developers or take other actions on the issue.
By setting the target version of an issue to a version that is not yet released, the issue shows up on the project roadmap, providing user with information about when to expect the issues to be resolved.
The roadmap page has a section for each release showing information like planned issues, issues done and percentage of issues completed.
Issues that are fixed in a specific version, but didn't have the target_version field set, will not show up in the roadmap.
This allows the ability to control the issues that are significant enough to show in the roadmap, while all resolved fields can be found in the change log.
Note that it is possible to set the 'target version' for multiple issues using the 'Update Target Version' group action that is available through the "View Issues" page (below the issues list).
This option is only available when the current project is not 'All Projects'.
Although it is not a typical scenario, it is worth mentioning that once a version is marked as obsolete, it is not included in the roadmap.

Note that the roadmap only includes future versions, once a version is marked as released, it no longer is included in the roadmap.
For information about such releases, the change log feature should be used.
For an issue to be shown on the roadmap, it has to have the target version set.
It does not matter whether the feature is resolved or not.
Resolved features will be decorated with a strikethrough and will be counted as done.

