# Example of Create File and directory management

1. `mkdir scripts`
2. `cd scripts`
3. `vim first_script.sh`
   - ```Shell
      mkdir -p dir1
      echo "Hello Bash World!!" > dir1/file.txt
      tree .
      cat dir1/file.txt
     ```
4. `chmod +x first_script` or `chmod 700 first_script`
5. `./first_script.sh`  
   To make a shortcut without into the directory file, you can define a new variable in `.bashrc` file, like this `export PATH="$PATH:~/scripts"`. So you can just call `first_script.sh`

# What is Shebang?

A shebang is a common name for the `#!` notation used in the first line of a script to indicate how it should be run. It's a way to specify the interpreter for a script, particularly in Unix-like operating systems. For example, `#!/bin/bash` would indicate that the script should be run with the Bash shell.  
you can check intrepreter with this `which bash` for bash, and `which python` for pyhton

## Example Shebang in files

1. Bash Language

```Shell
	#!/bin/bash
	mkdir -p dir1
        echo "Hello Bash World!!" > dir1/file.txt
        tree .
        cat dir1/file.txt
```

2. Python Langugae

```Python
	#!/home/rasyidannas/anaconda3/bin/python
	import sys
	print(sys.version)
```

# What is Variable and How defined it

A variable is a name for a memory loaction where a value (which can be manipulated) is stored.
Variable naming convensions in Bash:

1. Use lower_case variable names (snake_case)
2. constants should be written in CAPITALS
3. Varibale names cannot start with a number and cannot contain spaces or other special characters

Example of define variable:

```Bash
os=Linux
distro="Kali Linux"
age=25
distro="Ubuntu"
my_distro="$os $distro"
fruits=(apple banana cherry) # this is for declare array
echo ${fruits[1]}
echo $my_distro
```

you can find variable using `set | grep [variable_name]`, for print variable `echo $[variable_name]` or `echo ${[variable_name]}` and for remove variable use this `unset [variable_name]`.

## How to declare constant variable

You should write `declare [option] [variable_name]=[value]`. Example for declare with provided value from another file `declare -r LOGDIR=/var/log`.

## How to do Variable Assigning & Expansion

1. Assigning a value to a variab;e
   `version=10` _no space around the equal sign_
2. Referencing the value of a variable
   `echo $version` _the $ character introduces parameter expansion, command substitution, or arithmetic expansion._

## How about Quoting

Quoting is used to remove the special meaning of certain characters or words.  
Bash Quoting Mechanisms:

1. Single quotes => ''
2. Double quotes => "" _this is more prefer use because it can read refernce variable and escape charcter_
3. The escape character => \

## What is Environment vs Shell Local Variables

1. Environment variables
   - are inherited by any child shells or processes
   - used to padd information to processes that are spawwned from the current sheel
   - displayed using `env` or `printenv`
2. Shell Variables
   - are contained exclusively within the shell in which they were set and temporary
   - display using set

## How to get user input as variables

you can use `read [variable_name]` and then enter the value, if you don't write variable_name or only `read`, you can call it `echo $REPLY`

## What is Positional Parameters?

In programming, positional parameters are a type of function or method parameters that are identified by their position in the function or method call. This is example in bash language `apt install nginx`, `apt` is script name | `install` is first argument | and `nginx` is second argument
