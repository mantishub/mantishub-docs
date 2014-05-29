==============
Importing Data
==============

Import Csv Files
################

To import issues from an Excel or CSV, do the following:

- Go to "Manage" - "Manage Plugins"
- Click install next to "Mantis CSV Importer" plugin.
- Select the project to import the issues into.
- In case of Excel format, save as CSV with comma or semi-colon as the separator.
- Select CSV with issues related to the above project with one row per issue.  Use '\n' to represent new lines.
- Go to "Manage" - "Import CSV file"
- First wizard page - enable creation of categories and set the separator character.
- Second wizard page - allows mapping csv columns to MantisHub fields.

Each issue should be represented by one line (row) in the csv file.
