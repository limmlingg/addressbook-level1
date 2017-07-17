# AddressBook (Level 1)
* This is a CLI (Command Line Interface) Address Book application **written in procedural fashion**. 
* It is a Java sample application intended for students learning Software Engineering while using Java as 
  the main programming language. 
* It provides a **reasonably well-written** code example that is **significantly bigger** than what students 
  usually write in data structure modules. 
* It can be used to achieve a number of beginner-level learning outcomes without running into the complications
  of OOP or GUI programmings.

**Table of Contents**
* [**User Guide**](#user-guide)
    * [Starting the program](#starting-the-program)
    * [List of commands](#list-of-commands)
* [**Developer Guide**](#developer-guide)
    * [Setting Up](#setting-up)
    * [Design](#design)
    * [Testing](#testing)
* [**Contributors**](#contributors)
* [**Contact Us**](#contact-us)

-----------------------------------------------------------------------------------------------------
# User Guide

This product is not meant for end-users and therefore there is no user-friendly installer. 
Please refer to the [Setting up](#setting-up) section to learn how to set up the project.

## Starting the program

**Using Eclipse**

1. Find the project in the `Project Explorer` or `Package Explorer` (usually located at the left side)
2. Right click on the project
3. Click `Run As` > `Java Application`
4. The program now should run on the `Console` (usually located at the bottom side)
5. Now you can interact with the program through the `Console`

**Using Command Line**

1. 'Build' the project using Eclipse
2. Open the `Terminal`/`Command Prompt`
3. `cd` into the project's `bin` directory
4. Type `java seedu.addressbook.AddressBook`, then <kbd>Enter</kbd> to execute
5. Now you can interact with the program through the CLI

## List of commands
#### Viewing help: `help`
Format: `help` 
 > Help is also shown if you enter an incorrect command e.g. `abcd`
 
#### Adding a person: `add`
> Adds a person to the address book

Format: `add NAME p/PHONE_NUMBER e/EMAIL`  
> Words in `UPPER_CASE` are the parameters<br>
  Phone number and email can be in any order but the name must come first.

Examples: 
* `add John Doe p/98765432 e/johnd@gmail.com`
* `add Betsy Crowe e/bencrowe@gmail.com p/1234567 `

#### Listing all persons: `list`

> Shows a list of persons, as an indexed list, in the order they were added to the address book, 
oldest first.

Format: `list`  

#### Finding a person by keyword `find`
> Finds persons that match given keywords

Format: `find KEYWORD [MORE_KEYWORDS]`  
> The search is case sensitive, the order of the keywords does not matter, only the name is searched, 
and persons matching at least one keyword will be returned (i.e. `OR` search).

Examples: 
* `find John`
  > Returns `John Doe` but not `john`
   
* `find Betsy Tim John`
  > Returns Any person having names `Betsy`, `Tim`, or `John`

#### Deleting a person: `delete`

Format: `delete INDEX`  
> Deletes the person at the specified `INDEX`. 
  The index refers to the index numbers shown in the most recent listing.

Examples: 
* `list`<br>
  `delete 2`
  > Deletes the 2nd person in the address book.
  
* `find Betsy` <br> 
  `delete 1`
  > Deletes the 1st person in the results of the `find` command.

#### Clearing all entries: `clear`
> Clears all entries from the address book.  
Format: `clear`  

#### Exiting the program: `exit`
Format: `exit`  

#### Saving the data 
Address book data are saved in the hard disk automatically after any command that changes the data. 
There is no need to save manually.

#### Changing the save location
Address book data are saved in a file called `addressbook.txt` in the project root folder.
You can change the location by specifying the file path as a program argument.

Example:

* `java seedu.addressbook.AddressBook mydata.txt`
* `java seedu.addressbook.AddressBook myFolder/mydata.txt`

> The file path must contain a valid file name and a valid parent directory.<br>
  File name is valid if it has an extension and no reserved characters (OS-dependent).<br>
  Parent directory is valid if it exists.<br>
  Note for non-Windows users: if the file already exists, it must be a 'regular' file.<br>

> When running the program inside Eclipse, there is a way to set command line parameters
  before running the program.

-----------------------------------------------------------------------------------------------------
# Developer Guide

## Setting up

**Prerequisites**

* JDK 8 or later 
* Eclipse IDE

**Importing the project into Eclipse**

1. Open Eclipse
2. Click `File` > `Import`
3. Click `General` > `Existing Projects into Workspace` > `Next`
4. Click `Browse`, then locate the project's directory
5. Click `Finish`

## Design

AddressBook saves data in a plain text file, one line for each person, in the format `NAME p/PHONE e/EMAIL`.
Here is an example:

```
John Doe p/98765432 e/johnd@gmail.com
Jane Doe p/12346758 e/jane@gmail.com
```

All person data are loaded to memory at start up and written to the file after any command that mutates data.
In-memory data are held in a `ArrayList<String[]>` where each `String[]` object represents a person.


## Testing

**Windows**

1. Open a DOS window in the `test` folder
2. Run the `runtests.bat` script
3. If the script reports that there is no difference between `actual.txt` and `expected.txt`, 
   the test has passed.

**Mac/Unix/Linux**

1. Open a terminal window in the `test` folder
2. Run the `runtests.sh` script
3. If the script reports that there is no difference between `actual.txt` and `expected.txt`, 
   the test has passed.

**Troubleshooting test failures**

* Problem: How do I examine the exact differences between `actual.txt` and `expected.txt`?<br>
  Solution: You can use a diff/merge tool with a GUI e.g. WinMerge (on Windows)
* Problem: The two files look exactly the same, but the test script reports they are different.<br>
  Solution: This can happen because the line endings used by Windows is different from Unix-based
  OSes. Convert the `actual.txt` to the format used by your OS using some [utility](https://kb.iu.edu/d/acux).
* Problem: Test fails during the very first time.<br>
  Solution: The output of the very first test run could be slightly different because the program
  creates a new storage file. Tests should pass from the 2nd run onwards.

-----------------------------------------------------------------------------------------------------
# Contributors

* [Jeffry Hartanto](http://github.com/jeffryhartanto): Created a ToDo app that was used as the basis for this code.
* [Leow Yijin](http://github.com/yijinl): Main developer for the first version of the AddressBook-level1
* [Damith C. Rajapakse](http://www.comp.nus.edu.sg/~damithch): Project Advisor

-----------------------------------------------------------------------------------------------------
# Contact Us

* **Bug reports, Suggestions**: Post in our [issue tracker](https://github.com/se-edu/addressbook-level1/issues)
  if you noticed bugs or have suggestions on how to improve.
* **Contributing**: We welcome pull requests. Follow the process described [here](https://github.com/oss-generic/process)
