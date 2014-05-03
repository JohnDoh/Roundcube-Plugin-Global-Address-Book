Roundcube Webmail GlobalAddressbook
===================================
This plugin adds an SQL based global address book to Roundcube. It can be
global per installation, per IMAP host or per domain.

License
-------
This plugin is released under the [GNU General Public License Version 3+][gpl].

Even if skins might contain some programming work, they are not considered
as a linked part of the plugin and therefore skins DO NOT fall under the
provisions of the GPL license. See the README file located in the core skins
folder for details on the skin license.

Install
-------
* Place this plugin folder into plugins directory of Roundcube
* Add globaladdressbook to $config['plugins'] in your Roundcube config

**NB:** When downloading the plugin from GitHub you will need to create a
directory called globaladdressbook and place the files in there, ignoring the
root directory in the downloaded archive.

Config
------
The default config file is plugins/globaladdressbook/config.inc.php.dist
Rename this to plugins/globaladdressbook/config.inc.php

**'username'**

This is the name of the dummy user which holds the global address book.
The username does not have to belong to a valid email account. The username
will be stored in the Roundcube database but will not be able to log into
Roundcube unless it belongs to a valid email account on your server.

To create a single global address book for everyone who access Roundcube set
this options to something like: '[global_addressbook_user]'

To create a global address book per email domain which Roundcube serves set
this options to something like: 'global_addressbook@%d'

The username can contain the following macros that will be expanded as
follows:
* %d is replaced with the domain part of the logged in user's username
* %h is replaced with the imap host (from the session info)

**'readonly'**

Make address book read only, users will not be able to edit the contents of the
address book or add new contacts

**'groups'**

Should contact groups be available in the global address book

**'admin'**

The admin is a user or users who will always have full read/write access even
if the address book is set to read only. The follow options are available:
* To set a single user as admin then enter their username as a string like:
  'admin@domain.com'
* If you wish give admin rights to multiple users then enter the usernames in
  an array like: array('admin1@domain.com', 'admin2@domain.com')
* You can also use regual expressions to match the admin username, regular
  expressions must be started and finished the a '/'. Eg: '/^admin@/'

**'autocomplete'**

Show contacts from this book in the auto complete menu when composing an email

[gpl]: http://www.gnu.org/licenses/gpl.html