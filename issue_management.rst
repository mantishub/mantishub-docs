================
Issue Management
================

Issue Lifecycle
###############

An important part of issue tracking is to classify issues as per their status.
MantisHub assumes that an issue can be in one of three stages: opened, resolved and closed.
MantisHub has the following statuses: new, feedback, acknowledged, confirmed, assigned, resolved and closed.
Statuses "new" -> "assigned" map to opened, "resolved" means resolved and "closed" means closed.

Following is the explanation of what each status means:

- **New** - This is the landing status for new issues.
  The next status is typically "feedback", "acknowledged", "confirmed", "assigned" or "resolved".

- **Feedback** - This status is used to reflect that the issue is pending on feedback from the reporter.
  The next status is typically "new", "assigned", or "resolved".

- **Acknowledged** - This status is used by the development team to reflect their agreement to the suggested feature request.
  Or to agree with what the reporter is suggesting, although they didn't yet attempt to reproduce what the reporter is referring to.
  The next status is typically "assigned" or "confirmed".

- **Confirmed** - This status is typically used by the development team to reflect that they agree with what the reporter is suggesting in the issue and that they have confirmed and reproduced the issue.
  The next status is typically "assigned".

- **Assigned** - This status is used to reflect that the issue has been assigned to one of the team members and that such team member is actively working on the issue.
  The next status is typically "resolved".

- **Resolved** - This status is used to reflect that the issue has been resolved.
  An issue can be resolved with one of many resolutions.
  For example, an issue can be resolved as "fixed", "duplicate", "won't fix", "no change required", etc.
  The next statuses are typically "closed" or in case of the issue being re-opened, then it would be "feedback".

- **Closed** - This status reflects that the issue is completely closed and no further actions are required on it.
  It also typically hides the issue from the View Issues page.
  Some teams use "closed" to reflect sign-off by the reporter and others use it to reflect the fact that the fix has been released to customers.

Reporting an Issue
##################

Once a project has been defined, issues can be reported against it by users who have access level REPORTER or above.
Following are the steps:

- In case there is more than one project, make sure the appropriate project is selected at the top right of the screen.
- Enter the issue details -- category, summary and description fields are mandatory.
- Submit the issue.
