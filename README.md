# Common Commands/Instructions that I usually need to reference
Instead of having to google common commands, I am putting them here for faster reference. Anything inside of the `<` `>` symbols is to be changed by the user for their specific use case. The actual typed commands themselves should NOT include the `<` `>` symbols.

Anyhhing to the right of a `#` is a comment.

## Installing Ubuntu

## Command-Line (For linux)
Entering the terminal (i.e. command-line, i.e. shell): Press the `HOME` button on your keyboard. Type in `cmd`. Click on `Terminal`. The directory (folder) that you are currently in should be displayed in txt on the leftmost side.

Navigating through the command line: the following commands let you change the directory (aka folder aka filepath) that you are currently in. This is called the "current working directory"
```
pwd #print current working directory
ls #list all sub-directories (i.e. sub-folders) in you current directory
cd <directory> #go into a sub-diretory (i.e. sub-folder) that is within your current working directory
cd .. # go up one directory level
cd   # go to your home directory
cd </home/user/path/to/directory> # go to a specific directory that is not in the saem path as your current working directory

mkdir <foldername> # create a new sub-directory from your current working directory
rm <foldername> #delete a sub-directory from your current working directory
rm <filename.filetype> #delete a file named 'filename.filetype' from your current working directory
```
Press the `UP` or `DOWN` arrows to automatically retype a previously typed command.

## Vim (i.e. a universal editor for most file types)

```
vim <filename.filetype>  # essentially you are entering the file named `filename.filetype` to view its contents. It creates a new file named `filename.filetype` if a file of that name doesn't already exist)
```
Press `ESC` to exit any mode. (Typing this an indefinite amount of times does no harm)

Type `i` to go into editing mode.

Highlighting text: To highlight text, ensure you first exit any mode that you are currently in by pressing `ESC`. Highlight a text by holding `CNTRL` and clicking on the terminal once (maybe need to click twice)

Copy by pressing `CNTRL+C`

Paste by pressing `CNTRL+v`

Press `Esc` to exit editable mode
Saving changes: Press`Esc`. Type `:w` to save any changes you made to the file
Exit a file: Press `Esc`. Type `:q` to exit the file (Type `:q!` to force exit the file if vim is not playing nice)

Indenting multiple lines. Type `v` to go into hilight mode. Move the hightlight with arrows. indent lines that are highlightes (google "vim indent multiple lines"), 

## Git
### Downloading someones elses git repository (i.e. online folder of their code) into your machine 
Find the Github repository you want to copy
Fork (copy) their repository into your github repository. This places a copy of their code into your Github profile which you now have full control over! (This is important becuase you cant commit changes to someone else repository unless they give you permission) (Google "how to fork a repository")
Go to your github, copy the gihub URL of your copy of their repository (URL should end in .git)
```
git clone <github URL> # github URL must come from your personal github repository (the URL can be pasted by pressing `CNTRL+V`)
```

Saving changes from your local repository to your github repository
```
git status
git pull
git add --all 
git status
git commit -m "comment saying what you changed"
git stash
git push
```

## Python
#### Interpreter
```
python # starts python interpreter (Interpreters check for errors and execute code on a line by line basis. Compilers check entire code for errors first line-by-line, then they execute the entire code line-by-line)

python pythonfile.py #executes an already existing python file that is found inside your current working directory 
```

#### Gym
```
import gym
import pybullet_envs
env_instance = gym.make('OctopusArm2DBulletEnv-v0', render=True)

```

#### Debugging
```
import os 
os.join("path/to/","directory/of/file.filetype") #joins two srtings to form one string a directory path

import inspect 
inspect.getfile(class_instance.__class__) #returns directory path to file, where the class is defined

#magic methods
print(class_instance.method.__doc__) #returns documentation for how to use method

import importlib
importlib.reload(previously_imported_module) # update a module within the python interpreter #https://stackoverflow.com/questions/684171/how-to-re-import-an-updated-package-while-in-python-interpreter

```

### Package Management
#### Installing a python module (i.e. software package) from source (source lets you modify the module)

```
#fork a repository first (google "how to fork a git repository")

cd <path/to/directory> #Go to the directory to where you want the package installed

git clone <github URL> #make sure you forked the repository first

ls #checks the contents of your current directory

#check if the repository name is shown

cd <name_of_folder_that_was_cloned> # go into folder you just downloaded

pip install -e . # Install the package using pip
```

## Checking which python modules (software packages) are installed in your current python environment

```
pip freeze # show list of installed packages

pip freeze | grep 'keyword' #List out all packages that have a specified keyword within their name
```
## Searching within your current directory
### Searching for a specific term in your directory

```
grep -r 'YOUR_SEARCH_TERM' .  # search all files (within your current directory and all sub-directories in it) for words that contain 'YOUR_SEARCH_TERM'
grep -r 'YOUR_SEARCH_TERM' </path/to/directory>  # search all files (within your </path/to/directory> directory and all sub-directories in it) for words that contain 'YOUR_SEARCH_TERM'
```

### Seaching for a specific file in your current directory

```
find . -name testfile.txt #looks for any files named `testfile.txt` that are contained within your current directory and its sub-directories
find </path/to/directory> -name testfile.txt #looks for any files named `testfile.txt` that are contained within </path/to/directory> directory and its sub-directories
```

## Viewing the contents of a file 
```
vim <filename.filetype> # one way
cat <filename.filetype> #another way
```

## Transferring files between a local and remote machine)
Copying the file "foobar.txt" from a remote host to the local host
```
scp your_username@remotehost.edu:foobar.txt /some/local/directory
```

Copying the file "foobar.txt" from the local host to a remote host
```
scp foobar.txt your_username@remotehost.edu:/some/remote/directory
```

Other scp commands (for entire directories and other intricacies) can be found at this website
```
http://www.hypexr.org/linux_scp_help.php
```

## Getting desired command-line commands to automatically run when you start a new terminal
Go to your bash file. this should be found in your home directoory and is named `.bashrc`
```
cd ~ # go to your home directory
vim .bashrc  # enter the file named `bashrc` for editing (creates a new file if it doesn't already exist)
```

Scroll to the very end of the .bashrc file 
Type `i` to be able to edit the file.
Copy and Paste the following (example lines) into the final line of the `.bashrc` file (to paste, use `cntrl+v`)
```
cd <path/to/directory> # makes the terminal start from a desired path
export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so # any process within a new shell now associates `LD_PRELOAD` with `/usr/lib/x86_64-linux-gnu/libGLEW.so`
```
Press `Esc` to exit editable mode
Type `:w` to save the changes, Type `:q` to exit the file, Type `:q!` to exit the file if vim is not playing nice

Now the these commands will run every time you open up a new command-line terminnal

## ROS
If you ever obtain the error "ERROR: Unable to communicate with master!", you need to open up a separate terminal and run:
```
roscore
```
