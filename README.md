# common-instructions
Instead of having to google common commands, I am putting them here for faster reference anything inside of the < > symbols os to be changed by the user for their specific use case

## instaling with git

Find the package you want to install online

```
git clone <github URL>
```

Go to the directory of the package you want to install
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

## view the contents in a file 
```
cat <filename>
```
