Elgg user importer from CSV files


========
CSV File

CSV files can be created from spreadsheet programs like Microsoft Excel by using the
Save As option and selecting the CSV format option. A csv file often has a header line
followed by a set of individual records like this:

	username,	name,	email
	george,		George,	george@test.com
	matt,		Matt,	matt@test.com
	sally,		Sally,	sally@test.com


==========
CSV Header

This importer provides three options for parsing the header line:

 1. There is no header so treat first line as a user record
 2. Skip first line
 3. Use names in the header to define mapping from column to field name


======
Fields

The 3 required fields are username, name, and email. There are two optional
fields of password and icon. If 3rd header option for using column names
is selected, custom fields can also be defined (but requires an additional
plugin). If using 1st or 2nd header option, columns must be ordered as
username, name, email, password, and icon with the last two being optional.

If password column is not defined or password is blank, a random password
is assigned to user.

Icon must be the filename with full path of an image located on server.
Web server must have permission to read the file. An example filename with
path is '/home/user/icons/george.jpg'. If you use 1st or 2nd header options,
you must include password column to add an icon.


=============
Notifications

Email notifications of new accounts can be sent to users. This is very
important if using random password assignment. Please test email notifications
on your server before importing users.
