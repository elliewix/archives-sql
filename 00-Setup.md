# 00-Setup

## 1: Install SQLite Studio

https://sqlitestudio.pl/index.rvt

This will be a regular program to run on your computer and shouldn't require anything extra strange.

## 2: Launch and load

We're going to load our data from the CSV file, but we have a little extra steps to take before we can dig into things.

* Launch SQLite Studio
* Our first step is to create a new database and connect to it 
  * In the database menu, secect "Add a database"
  * check that SQLIte3 is selected under Database Type
  * Click on the green `+` icon next to the file name box. navigate to a folder to save this file, and give it a name like 'letters' in in the Save As field.  Click OK.
  * Back in the new database dialog box, you'll see that your file name has been populated into the Name box. I suggest that you leave this as is.
  * Click OK
* On the left side of the application window, you should see the entry of `letters` appear.  Let's connect to it.
  * Right click on the name in the Databases pane.
  * Choose Connect to the database.
* Now we can act on our database, but we don't have data yet! Let's import a data file.
  * Right click on the `letters` entry in the Databases pane.
  * Choose `import`
  * In the empty box under Table, type in `pettigrew`, click Continue.
  * You'll see that you're in a new dialog box.
  * Check that the Data Source Type says CSV
  * Next to the input file box, click the folder icon. Use the file selector to identify the `pettigrew.csv` file. Click Open.
  * Ensure that the "First line represents CSV column names" check box is checked.
  * Click done.  (if it does nothing, then you need to connect to the database)
  
Great, now you can look next to the `letters` in the databases pane and see that there's now a drop down. Open up all those items, and you'll see the 4 column names under the Column node.

Let's go ahead and set our data types (you don't have to do this in some other SQLite gui programs.) By default, the columns were all imported without a datatype.  We're going to be exploring this more when we get into the actual lesson, but to try and put it simply: sqlite wants to know what kind of data is in each column.  This impacts how certain tools and searches work, so it does need to know.

For now, we're going to say that these are all `TEXT` columns.  Once you have all the column names visible (via clicking all the arrows to expand each item in the databases pane), you can right click on `BoxNumber` and select "Edit this column".  The window will change and a new dialog box will appear. 

In the Column dialog box, you should see the column name on the upper left.  Next to that will be a (likely empty) drop down box. Click it and select TEXT. Be careful! This menu item can be really touchy and might select one nearby.  Repeat this process over all the columns.  When you are done, you should see that the Data type column next to the column names all say TEXT. 

We are now ready to commit these changes into our database.  This is sort of like saving.  You can think of these GUIs as a tool to help you construct the SQL commands that you want. Now we've finished constructing them and need to execute that code.  We do this via clicking that green check box at the top (this has a check mark in it and not an 'x'.).  Clicking that will open up a prompt with the SQL code, which you don't need to change.  Click OK to have it execute that code. The bottom of the window should say that the changes were committed sucessfully.

Now we're ready to start digging into data! 


## Deprecated:  installation and setup using the FireFox plugin

Notes:  this tool no longer works with the new version of Firefox, but I'm leaving this here because it doesn't hut anything. 

We'll be using the Firefox [SQLite manager plugin](https://addons.mozilla.org/en-US/firefox/addon/sqlite-manager/) that should be installed on the lab computers or you can install it on your own computer.

Once the plugin is installed and Firefox is restarted, you can go up to Tools and select SQLite Manager to open up the wizard.

Time estimate:  20-30 minutes to get everyone on the same page.

## Directions for importing the data

Inside this repository is the `pettigrew.csv` file.  Be sure that you have access to that somewhere.  

1.  Click the blank paper icon in the upper left with the tooltip of "New Database"
2.  Type in `pettigrew` for the name.
3.  Click OK
4.  It'll take you to a window to show you where to save the database, just click "Open".
5.  You should now be back at the main SQLite Manager screen, and a new option is available at the top left.
6.  Click the icon of the blue disk with the arrow going into it with the tooltip of "Import"  (this near the New Database button).
7.  This should take you to an import wizard tool.  By default, CSV should be selected.
8.  Click "Select file" and naviate to the `pettigrew.csv` file on your computer. 
9.  Check the box that says "First row contains column names."
10. Ensure that the "Comma" option is selected for the "Fields separated by" section
11. Click to select the "Like MSExcel" for "Fields enclosed by"
12. Click ok.  
13. It will prompt you that a new table is being made.  Click OK to that.
14. A new window will appear where you can declare properties about the specific columns.
15. Change all the "Data Type" drop down options to "text" and leave everything else alone.
16. Click ok.
17. It will confirm with you again if you are sure and confirm that there are 601 rows to import. Click ok again.
18. Over on the left you should see that you now have an option of "pettigrew" under Tables.
19. You can now also use more features in the right hand section where there are tabs about Structure, Browse.
20. Click on Browse & Search, and you should see your data in tabular format.

Phew! Now you can actually start doing stuff.

## Next up

[Selecting Data](01-selecting-data.md)
