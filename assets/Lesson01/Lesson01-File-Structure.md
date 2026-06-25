A computer’s file structure is the way it organizes and stores files and folders so the operating system — and you — can find things efficiently. Understanding it is a foundational programming skill because developers constantly move between folders, create files, and run programs from the command line.

Imagine your computer as a giant filing cabinet:
- Folders (directories) are like drawers and folders in the cabinet.
- Files are the documents inside them.
- Folders can contain:
- more folders,
- files,
- or both.

Every file and folder has a path, which is like its address.

Example:  /Users/teresa/Projects/my-app/index.html

This means:
-	start at Users
-	go into teresa
-	then Projects
-	then my-app
-   then index.html

________________________________________

## Important File Structure Terms and Concepts

### Root Directory
- The root directory is the top of the file system hierarchy, represented as / on Unix-like systems.
- On Windows, root differs by drive (e.g., "C:\\" ).

________________________________________
### Absolute vs Relative Paths

Absolute Path: Starts from the root.

Example: **cd /Users/teresa/Projects**  moves you into the Project folder.

Relative Path: Starts from where you currently are.

If you're already in:  /Users/teresa

then: **cd Projects** also moves you into the Projects folder

________________________________________
## Important File Structure Commands

### Basic Navigation Commands
Commands are used in the terminal (command line).  

**pwd**  — Print Working Directory

**ls** — List Files

**cd**  — Change Directory / Move between folders

**cd Projects** - go into the projects folder 

**cd ..**  - Go back one level

**cd /**  - Go to the root directory
________________________________________
### Creating Files and Folders

**mkdir my-project**  - Create a folder

**touch index.html**  - Create an empty file

________________________________________
### Moving and Copying

**mv file.txt Documents/**  - Move a file

**mv old.txt new.txt**  - Rename a file

**cp file.txt backup.txt**  - Copy a file

________________________________________
### Removing Files

**rm notes.txt**  - Remove a file

Important note on **rm**.  it permanently deletes files and does not move them to trash in most terminal environments.

________________________________________
### Mental Model to Remember

Think of the terminal as:  “You standing in a folder giving instructions.”

Commands like:
- ls
- cd
- mkdir
all depend on where you currently are.

That’s why pwd is so important:  it tells you your current location in the file system.
