===========
MantisTouch
===========

What is MantisTouch?
####################

MantisTouch is a web app that provides a mobile optimized user interface for iPhone, Android, and Windows Phone.
Users who visit MantisHub from a mobile device, are automatically redirected to MantisTouch to get the mobile optimized experience.
Users can also access go their MantisTouch by going to the following url: (e.g. instance 'foo')

	https://foo.mantishub.com/m

Why MantisTouch?
################

Users are relying on their mobile devices more than ever.
As a user receives a MantisHub email notification, they click on it to get further details or comment on an issue.
If the MantisHub instance has MantisTouch enabled, the mobile optimized web app will be opened and will allow a better experience for the user.
That ultimately leads to higher productivity and better user experience.

Filtering
#########

MantisTouch supports the ability to filter issues that surface in the View Issues page.
This can be done via standard or custom filters.

The standard filters are available directly on the dashboard as well as via the filters page.
They include the following:

- All
- Assigned to Me
- Reported by Me
- Monitored by Me
- Unassigned

The custom filters are available via the filters page.
Any filter that is available to the user in MantisHub is also available in MantisTouch.
This includes filters created by the logged in user or ones created by others and shared with all users.
To add more filters, the user should use MantisHub standard desktop interface to apply a filter then save.

Features
########

MantisTouch provides mobile optimized experience for the following features:

- Browse through issue list
- View details of an issue
- Download attachments for an issue
- Edit an issue
- Delete an issue
- Comment on an issue
- Edit comment
- Delete comment
- Go to issue by id
- Filter issues by standard filters
- Filter issues by custom filters
- Report an issue
- Supports custom fields
- Accept auto-redirects from MantisHub when users visit it using a mobile device.
- Multi-project support

Supported Platforms
###################

MantisTouch is designed to work well on any mobile device that has a modern HTML 5 browser.
This includes platforms like iPhone, Android and Windows Phone.

Setting up on iPhone
####################

Here are the steps to add a home screen icon, similar to the ones for native apps:

- Go to Settings, Safari, and set "Accept Cookies" to "Always".
- Open Safari and browse to https://foo.mantishub.com/m/ (with foo being the instance name)
- Click the "share" arrow button and click "Add to Home Screen", then confirm "MantisTouch" name.
- Close Safari and run MantisTouch from the home page icon.

Setting up on Android
#####################

- Open the standard Android browser (not chrome, it is called 'Internet').
- Go to https://foo.mantishub.com/m/
- Click Menu, then 'Add Shortcut to Homepage'
