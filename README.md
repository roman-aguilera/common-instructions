# Common Commands/Instructions that I usually need to reference
Instead of having to google common commands, I am putting them here for faster reference anything inside of the < > symbols os to be changed by the user for their specific use case

## Git
### Copying someones elses folder (repository)
Find the package you want to install online

Cloning(copying) a github repository
```
#fork to your own gihub repository first (you cant commit changes to someon else repository unless)
git clone <github URL> # github URL must come from your personal github repository
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
### Interpreter

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

#### Package Management
### Installing a python module (i.e. software package) from source (source lets you modify the module)

```
cd <path/to/directory> #Go to the directory to where you want the package installed

git clone<>

cd <folder of packages you just downloaded with git> 
```

```
ls #check the content of your curretn directory
```

Install the package using pip
```
pip install -e .
```

## View the Packages installed in your pip
View list of packages installed
```
pip freeze
```

List out all packages that have a specified keyword
```
pip freeze | grep <keyword>
```
## Search within your current directory
### Looking for specific term in your directory
This looks for a term in all the files contained within your current directory. If you want to specify a directory that is not the current directory, replace the '.' at the end with a directory.
```
grep -r 'YOUR_SEARCH_TERM' .
```

## Looking for a specific file in your current directory
This looks for a files contained within your current directory and sub-directories. If you want to specify a directory that is not the current directory, replace the '.' at the end with a directory.
```
find . -name testfile.txt
```

## View the contents in a file 
```
vim <filename> # one way
cat <filename> #another way
```

## Copying and pasting files between a local and remote machine)
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

## Making command line commands automatically run when a new terminal pops up
Go to your bash file. this should be found in your home directoory and is named `.bashrc`
```
cd ~ # go to your home directory
vim .bashrc  # enter the file named `bashrc` for editing (creates a new file if it doesn't already exist)
```

Scroll to the very end of the .bashrc file and paste the following into the final line of the `.bashrc` file
```
cd <path/to/directory> # makes the terminal start from a desired path
export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so # any process within a new shell now associates `LD_PRELOAD` with `/usr/lib/x86_64-linux-gnu/libGLEW.so`
```
Now the this will run every time you open up a command line terminnal

## ROS commands
If you ever obtain the error "ERROR: Unable to communicate with master!", you need to open up a separate terminal and run:
```
roscore
```
