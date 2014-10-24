=======
Filters
=======

This section covers MantisHub capabilities around filtering.  MantisHub filters enables
users to filter the issues by criteria that they specify via the web interface.  Such
filters can be saved, re-used and shared.  Filters can include criteria for both native
and custom fields.

Saving Filters
--------------

By default, MantisHub stores the latest adhoc filter per project.  So that users retain
their latest filters between login sessions, or as they switch between projects.

However, it is often useful to share filters so that the user is able to easily switch
between them.  MantisHub allows users to do that by setting up the filter and then selecting
"Save Current Filter" and then giving it a friendly name.

Sharing Filters
---------------

When saving a filter, users have the option of marking filters as public or not.  Public
filters are shared with all users.  This is a useful feature when defining common filters
that the whole teams need to be able to use.  For example, "blocking issues" or "next release".
If the filter is limited to a project, then it is only shared with users who have access
to that project.

All Projects vs. Current Project
--------------------------------

When saving a filter, users have the option to make it available for "All Projects" vs.
just the current project.  Project specific filters may be based on project specific custom fields,
versions, or categories along with other fields.  Project specific filters will only be available for
selection when their associated project is active.

Semantic Values
---------------

Filters often are based on static values like "v1" for a version.  However, in other cases
it is desirable to use semantic values.  Such values include
- [any] - don't filter on this field.
- [none] - field must not be set (e.g. issue not assigned).
- [myself] - issue assigned to the logged in user.

Now, why would we need "[myself]" compared to "vboctor".  Such value is very important when
defining filters with the intention of sharing.  For example, "My Blocking Issues" can be 
defined as: priority=blocking and assign-to=[myself].  Then this filter can be saved as
Public (i.e. shared with all users) and All Projects (i.e. applies to all projects).

Simple vs. Advanced
-------------------

By default MantisHub uses simple filters which allows users to filter on one value per field,
allowing filters like priority=immediate and severity=block.  However, in
some cases it is necessary leverage advanced filters to define criteria like 
(priority=urgent OR immediate) and (severity=block OR crash).

Filters through API
-------------------

Once a filter is defined via the web UI, the filter is made available via the SOAP API.
Clients can leverage the SOAP API to get list of filters and then use any of them and query
matching issues.  In addition, the SOAP API exposes a set of standard out-of-the-box filters
like "Reported by Me", "Assigned to Me", "Unassigned", "Monitored by Me".

