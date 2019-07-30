# common-instructions
Instead of having to google common commands, I am putting them here for faster reference anything inside of the < > symbols os to be changed by the user for their specific use case

## instaling with git

Find the package you want to install online

```
git clone <github URL>
```

## Go to the directory of the package you want to install
```
cd <folder of packages you just downloaded with git>
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

## Look for specific term
This looks for a term in all the files contained within your current directory. If you want to specify a directory that is not the current directory, replace the '.' at the end with a directory.
```
grep -r 'YOUR_SEARCH_TERM' .
```

## Look for a specific file
This looks for a files contained within your current directory and sub-directories. If you want to specify a directory that is not the current directory, replace the '.' at the end with a directory.
```
find . -name testfile.txt
```

## View the contents in a file 
```
cat <filename>
```

## Having commands automatically run when a terminal pop up
Go to your bash file. this should e found in your home directoory and is named .bashrc
```
cd ~
vim .bashrc
```

Scroll to the very end of the .bashrc file and paste the following on the final line
```
export LD_PRELOAD=/usr/lib/x86_64-linux-gnu/libGLEW.so
```
Now the this will run every time you open up a command line terminnal

## ROS commands
If you ever obtain the error "ERROR: Unable to communicate with master!", you need to open up a separate terminal and run:
```
roscore
```
