===
API
===

Overview
--------

MantisHub offers a SOAP webservice API that allows remotely accessing
MantisHub from your language of choice.

WSDL and Endpoint
-----------------

Here is a sample instance WSDL definition:
https://mantishub.mantishub.com/api/soap/mantisconnect.php?wsdl

To access the target instance replace the first "mantishub" in the URL above
with the instance name.  Note that API is not available for Bronze plan.

API Version
-----------

The API shares the same version with MantisHub.  Such version can be retrieved via the following API.  This is typically the first API called.

- mc_version - gets the version of the MantisHub instance.

Issue Management
----------------

- mc_issue_exists - check if an issue exists.
- mc_issue_get - gets the details of the specified issue.
- mc_issue_get_history - gets the history for the specified issues.
- mc_issue_get_biggest_id - gets the id of the last issue reported.
- mc_issue_get_id_from_summary - gets the id of an issue given its summary (title).
- mc_issue_add - submits an issue.
- mc_issue_update - updates an issue.
- mc_issue_set_tags - tag an issue.
- mc_issue_delete - delete an issue.
- mc_issue_note_add - submit a comment.
- mc_issue_note_delete - delete a comment.
- mc_issue_note_update - update a comment.
- mc_issue_relationship_add - add issue relationship.
- mc_issue_relationship_delete - delete issue relationship.
- mc_issue_attachment_add - add issue attachment.
- mc_issue_attachment_delete - delete issue attachment.
- mc_issue_attachment_get - get issue attachment info.
- mc_issue_checkin - Notifies MantisBT of a check-in for the issue with the specified id. (deprecated feature)

Custom Fields
-------------

- mc_enum_custom_field_types - gets the custom field definition types.

Tags
----

- mc_tag_get_all - get all defined tags.
- mc_tag_add - add a tag.
- mc_tag_delete - delete a tag.

Filters
-------

- mc_filter_get - get the filters defined for the specified project.
- mc_filter_get_issues - get the issues that match the specified filter and paging details. Pass "-1" for the per_page parameter to get all issues.
- mc_filter_get_issue_headers - get the issue headers that match the specified filter and paging details. Pass "-1" for the per_page parameter to get all issues.

Configs
-------

- mc_config_get_string - get the value for the specified configuration variable.
- mc_enum_status - gets the enumeration values and labels for statuses.
- mc_enum_priorities - gets the enumeration values and labels for priorities.
- mc_enum_severities - gets the enumeration values and labels for severities.
- mc_enum_reproducibilities - gets the enumeration values and labels for reproducibilities.
- mc_enum_projections - gets the enumeration values and labels for projections.
- mc_enum_etas - gets the enumeration values and labels for ETAs.
- mc_enum_resolutions - gets the enumeration values and labels for resolutions.
- mc_enum_access_levels - gets the enumeration values and labels for access levels.
- mc_enum_project_status - gets the enumeration values and labels for project statuses.
- mc_enum_project_view_states - gets the enumeration values and labels for project view states.
- mc_enum_view_states - gets the enumeration values and labels for issue view states.
- mc_enum_get - gets the enumeration values and labels given its name.

Project Management
------------------

- mc_project_add - create a project.
- mc_project_delete - delete a project (and all issues under it).
- mc_project_update - update project information.
- mc_project_get_id_from_name - get project id given its name.
- mc_project_get_issues_for_user - get issues assigned to a user, reporter by user, monitored by user, etc.
- mc_project_get_issue_headers - get header information for issues.
- mc_project_get_users - get users explicitly added to the project.
- mc_projects_get_user_accessible - get projects accessible to the user.
- mc_project_get_categories - get categories associated with the project.
- mc_project_add_category - add a category to the specified project.
- mc_project_delete_category - delete category from specified project.
- mc_project_rename_category_by_name - rename a category.
- mc_project_get_versions - get versions associated with the specified project.
- mc_project_version_add - adds a project version.
- mc_project_version_update - updates a project version.
- mc_project_version_delete - delete a project version.
- mc_project_get_released_versions - get project versions that are marked as released.
- mc_project_get_unreleased_versions - get project versions that are marked as unreleased.
- mc_project_get_attachments - get project documents (deprecated feature).
- mc_project_get_custom_fields - get custom fields associated with the project.
- mc_project_attachment_get - get project document (deprecated feature).
- mc_project_attachment_add - adds a project document (deprecated feature).
- mc_project_attachment_delete - deletes a project document (deprecated feature).
- mc_project_get_all_subprojects - gets list of sub-projects.

Users
-----

- mc_login - validate user credentials and return information about the user account.
- mc_user_pref_get_pref - gets user preferences
- mc_user_profiles_get_all - gets environment profiles associated with user.

Client Libraries
----------------

- C# - MantisConnect @ http://www.futureware.biz/mantisconnect/
