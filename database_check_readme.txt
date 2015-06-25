Database check tool (v1.0) 
Designed and tested for osCommerce v2.2.
v1.1  22/5/08 - Geoffrey Walton
Enabled sites where admin folder is not called admin to use this excellent tool. - Geoffrey Walton
Added language support for a few more fields, description, table titles.
v1.2  22/5/08 - Geoffrey Walton
Added product model to some tables and corrected speelink mistoikes.
v1.3 28/09/11 - Geoffrey Walton
Corrected error where parts without a description or manufacturer were not being shown.
Added functionality to set a default wt and put a product into a category.
v1.4 20/6/14 - Geoffrey Walton
Added 6 more utilities and converted for 2.3.4
v 1.6 10/8/14 - Geoffrey Walton
Added more checks, there are now 18.
Changed references to mysqli to use tep functions.
Made it multi-lingual but did not translate it.
v 1.7 1/11/14 - Geoffrey Walton
Corrected spelling mistakev 
1.8 19/11/14 - Geoffrey Walton
Manufacturers with no products can now be deleted.
Categories and parts where there are no description records or the nameis blank are highlighted.
If the description is blank these are not shown. Title text amended to reflect this.
-----------------------------------------------------------------------------------------------

This modification includes these features:

* Seven different checks for various record exceptions

1. Duplicate product names
2. Products no title
3. Products no price
4. Products no weight
5. Products no category
6. Categories no products
7. Duplicate products to categories

* Step-by-step process to make routine checking easier

* Pre-populated links to edit exceptions found.  (Edited through categories.php)

* Additional information listings about each product or category found

* Main menu to perform checks in any order

* Ability to delete products or categories

* Refreshed/updated results after delete

* Easy install with minimal file editing

* Prompting before delete  (Are you sure you want to delete?)

-----------------------------------------------------------------------------------------------

Files included:

* admin/database_check.php
* admin/includes/functions/dbcheck.php
* admin/includes/languages/database_check.php

Buttons included:

* admin/includes/languages/english/images/buttons/button_delete.gif
* admin/includes/languages/english/images/buttons/button_main.gif
* admin/includes/languages/english/images/buttons/button_new_product.gif
* admin/includes/languages/english/images/buttons/button_next.gif
* admin/includes/languages/english/images/buttons/button_start.gif

-----------------------------------------------------------------------------------------------

Installation:

****  As always... BACKUP YOUR FILES!!! ****

1) Copy the files included to your server.  The delete button is the only thing you should 
already have in your store.  All other files in Database check tool are not used by any other 
programs.  (If you have changed your admin buttons you may or may not wish to replace your 
delete button with the one included).  Else, even if your store is heavily modified, you will 
not overwrite any of your files during this step.  The included .php files are only used by 
Database Check tool.  


2) In admin/includes/languages/english.php  anywhere before the end of the script:

ADD:

// Begin Database Check Tool
define('BOX_TOOLS_DATABASE_CHECK', 'Database Check');
// End Database Check Tool


3) In admin/includes/filenames.php  anywhere before the end of the script:

ADD:

// Begin Database Check Tool
define('FILENAME_DATABASE_CHECK', 'database_check.php');
// End Database Check Tool

4) In admin/includes/boxes/tools.php  (about line 32):

LOOK FOR:

      array(
        'code' => FILENAME_SEC_DIR_PERMISSIONS,
        'title' => BOX_TOOLS_SEC_DIR_PERMISSIONS,
        'link' => tep_href_link(FILENAME_SEC_DIR_PERMISSIONS)
      ),

REPLACE WITH THIS:

      array(
        'code' => FILENAME_SEC_DIR_PERMISSIONS,
        'title' => BOX_TOOLS_SEC_DIR_PERMISSIONS,
        'link' => tep_href_link(FILENAME_SEC_DIR_PERMISSIONS)
      ),
	  array(
        'code' => FILENAME_DATABASE_CHECK,
        'title' => BOX_TOOLS_DATABASE_CHECK,
        'link' => tep_href_link(FILENAME_DATABASE_CHECK)
      ),

THAT'S IT!!!

-----------------------------------------------------------------------------------------------

Additional notes:

At the time of making this tool, I am not aware of any contributions which will be interfered 
with in any way... even where products are assigned to multiple categories.  Those who have that 
modification installed can use this tool.  Checks to made to be sure that you are only deleting 
EXACT matches for your products with the SAME category id.  Unfortunately, at this time however, 
to those of you who have downloadable products... this tool will not deal with those products.  
Perhaps as time goes on, someone else will include it... or I will get to it if I can.

Please keep in mind that by design, duplicates should not occur in your osCommerce store's 
database.  However, it seems that sometimes... they just do.  Database check tool has been 
developed as a both a convenience and an aid in identifying anomalies or omissions that already 
exist.  It is not designed to help prevent these occurrences.  There are no guarantees made with 
this tool.  Should you choose to use it... you do so at your own risk!!!  If you are getting 
duplicates in your database frequently or inconsistent results from queries ... and they are 
not caused by human error, you should fix this right away.  Remember, the life line of your 
store is your database.  The store will only run as well as it's life line allows it to!!!

Remember:  There ARE clickable links within the results you find from your store.  Before you
delete or change anything, you should either be 100% sure that you would like to make a change
or check each entry out before making an action.  There is plenty of information to help you
with this... so just take the extra moment(s) necessary to avoid costly errors.

If you have any suggestions on how this tool can improve performance or checks that it should 
perform, please do not hesitate to say so.  I will assist those who do need help with the 
installation process (if need be) as I can get time.  The best bet is usually to reach me in 
the forums.  You can look up the support thread for this tool called "Database check tool 
support" for this purpose.  This thread will have been created at the time of release.

I hope this helps both the experienced and the novice user keep their databases running 
efficiently and cleanly.  If you find this tool helpful, please let me know.  Surely, there 
will be updates to come in the future.  Stay tuned!

Good Luck!!!

Ohioman

If you get an "Internal Server Error" or as it is otherwise known a 500 error you can try
editing the values in /admin/database_check.php line 13.

	ini_set('max_execution_time', 300); //300 seconds = 5 minutes
	ini_set('memory_limit','128M');

http://forums.oscommerce.com/topic/338669-database-check-tool/

HTH

Geoffrey

