# Common Commands/Instructions that I usually need to reference
Instead of having to google common commands, I am putting them here for faster reference. Anything inside of the `<` `>` symbols is to be changed by the user for their specific use case. The actual typed commands themselves should NOT include the `<` `>` symbols.

Anyhhing to the right of a `#` is a comment.

## Installing Ubuntu
root (/) :8 GB  for 8Gb RAM
efi(mount as EFI): 260 (so that it can be 256)
swap(mount as swap): 

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

Undo most recent changes: Make sure to exit current mode by pressing `Esc`. Press `u`.

Editing mode: Press `i`.

Highlighting text: To highlight text, ensure you first exit any mode that you are currently in by pressing `ESC`. Highlight a text by holding `CNTRL` and clicking on the terminal once (maybe need to click twice)

Copy by pressing `CNTRL+C`

Paste by pressing `CNTRL+v`

Press `Esc` to exit editable mode
Saving changes: Press`Esc`. Type `:w` to save any changes you made to the file
Exit a file: Press `Esc`. Type `:q` to exit the file (Type `:q!` to force exit the file if vim is not playing nice)

Indenting multiple lines: Type `v` to go into visual mode. Hightlight text by moving up/down/left/right with arrow keys. Indent lines that are highlighted by typing `:s/^/<text_to_appear_at_the_beginning_of_each_line>` 

Going back and forth between editing a program and running it
https://stackoverflow.com/a/1258318/14024439

## GitHub

#### Downloading someones elses git repository (i.e. online folder of their code) into your machine 
Find the Github repository you want to copy
Fork (copy) their repository into your github repository. This places a copy of their code into your Github profile which you now have full control over! (This is important becuase you cant commit changes to someone else repository unless they give you permission) (Google "how to fork a repository")
Go to your github, copy the gihub URL of your copy of their repository (URL should end in .git)
```
git clone <github URL> # github URL must come from your personal github repository (the URL can be pasted by pressing `CNTRL+V`)
```

#### Saving changes from your local (computer's) repository to your github (online) repository
```
git status
git pull
git add --all 
git status
git commit -m "comment saying what you changed"
git stash
git push
```

#### Finding the top level directory of your local (computer's) repository
Say you are working on your code and it includes a lot of folders (and subfolders), but you are in one of the subfolders and forgot where exactly you originally put your repository when you downloaded (i.e. cloned or forked) it. Enter the following command

```
git rev-parse --show-toplevel
```

#### Inviting someine else to make changes on your repository

An "owner" in GitHub is someone that created a repository. A "contributor" in GitHub is someone that can make changes to an owner's repository.

The owner needs to go to webpage of repository where they want to add a contributor. For example `https://github.com/roman-aguilera/common-instructions` . click `setttings` (next to the gear symbol). Click on `manage access`. Click on green button that says `invte a collaborator`. Enter the username of contributor. Click the correct name of the contributor. Click the green button that says `select collaborator above`.

The contributor needs to go to the webpage that they are being asked to contribute to (e.g. `https://github.com/roman-aguilera/common-instructions`), but with `/invitations` appended at the end. For example ` https://github.com/roman-aguilera/common-instructions/invitations`. The contributor accepts the invitation there.

Reference: `https://stackoverflow.com/a/63052608/14024439`

Now, the "contributor" can download the owners code by going to the repository, clicking on the green button that says `code`, opying that url (e.g. `https://github.com/roman-aguilera/common-instructions.git`), downloading that file by running the command in the command line:

``` 
git clone <github URL> # generic command
git clone https://github.com/roman-aguilera/common-instructions.git #  example 
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
import pdb
pdb.set_trace() #sets pause and goes into debug mode. Commands that navigate this are `n` (next line), `s` (step  one level deeper until next function call), there are other commands that I don't know off the top of my head.

import os 
os.join("path/to/","directory/of/file.filetype") #joins two srtings to form one string a directory path

import inspect 
inspect.getfile(class_instance.__class__) #returns directory path to file, where the class is defined

#magic methods
print(class_instance.method.__doc__) #returns documentation for how to use method

import importlib
importlib.reload(previously_imported_module) # update a module within the python interpreter #https://stackoverflow.com/questions/684171/how-to-re-import-an-updated-package-while-in-python-interpreter

```

#### Package Management
##### Installing a python module (i.e. software package) from source (source lets you modify the module)

```
#fork a repository first (google "how to fork a git repository")

cd <path/to/directory> #Go to the directory to where you want the package installed

git clone <github URL> #make sure you forked the repository first

ls #checks the contents of your current directory

#check if the repository name is shown

cd <name_of_folder_that_was_cloned> # go into folder you just downloaded

pip install -e . # Install the package using pip
```

#### Checking which python modules (software packages) are installed in your current python environment

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

## Customizing your computer so that you have specific command-line commands automatically run when you start a new terminal (i.e. black screen where you code)
Go to your bash file. this should be found in your home directoory and is named `.bashrc`
```
cd ~ # go to your home directory
vim .bashrc  # enter into the file named `.bashrc` for editing (creates a new file if it doesn't already exist)
```
Should be located under ```conda initialize```

Scroll to the very end of the .bashrc file 
Type `i` to be able to edit the file.
Type in whatever command you want to run. Press `Esc`. Press `:w`, press, `Enter` to save the changes to that file. Press `:q`, press `Enter`, to exit the file and go back to the command line.

Refer below to to the following example commands that you can add to the end of your `.bashrc` file. (Note: To copy text within the terminal, highlight the text with your mouse, press `shift+cntrl+c`. To paste text within the terminal, use `shift+cntrl+v`.)
```
cd <your/specific/path/to/desired/directory> # makes the terminal start from a desired path
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
