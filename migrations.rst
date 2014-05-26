.. _migrations:

======================
Migrating to MantisHub
======================

What bug trackers can I migrate from?
#####################################

At this point we support migrations from MantisBT.
However, let us know what bug trackers you would like to migration from.

Are there any restrictions on what can be migrated?
###################################################

We don't support the following:

- Code customizations
- Migration from databases other than MySQL.
- Use of deprecated features (e.g. news, project docs, FTP attachments).
- Custom plugins that are not offered by MantisHub.

However, we support config customization, hence, any config overrides you had will work in MantisHub.

What is the process for migration?
##################################

- Signup for a trial using the plan and subdomain name that you would like to migrate to.
- Feel free to try out the MantisHub experience.  Any data entered into the trial will be discarded when your instance is migrated.
- Provide support with your database and attachment data to be migrated.
- Once migrated, you won't have to worry anymore about backups, upgrades, etc.
  You will be able to enjoy the MantisHub experience similar to users who started in MantisHub.

Preparing data for Migration
############################

- If your MantisBT instance is not on MantisBT v1.2.x, then upgrade to 1.2.x.
- Set $g_absolute_path_default_upload_folder in config_inc.php to point to target upload folder.
- Go to each project settings page and make sure it has the upload folder set.
- Export database attachments to disk via http://www.example.com/mantis/admin/system_utils.php
- Dump database "mysqldump -u [database_user] -p[database_password] [database_name] > [mysql_dump_file_path]".  Replace parameters between square brackets with real values.
- Create a folder on OneDrive, GoogleDrive, or Dropbox and share it with victor@mantishub.com - don't require signup.
- Copy config files like config_inc.php, custom_strings_inc.php (optional), custom_constants_inc.php (optional), custom_relationships_inc.php (optional) to the shared folder.
- Copy a zipped version of the mysql dump to the shared folder.
- Copy a zipped version of all attachments to the shared folder.
- Contact support and we will arrange your migration.  We offer migrations over weekends to avoid downtime for your users.
