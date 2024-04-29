# Example of Create File and directory management
1. `mkdir scripts`
2. `cd scripts`
3. `vim first_script.sh`
     * ``` Shell
        mkdir -p dir1
        echo "Hello Bash World!!" > dir1/file.txt
        tree .
        cat dir1/file.txt
       ```
5. `chmod +x first_script` or `chmod 700 first_script`
6. `./first_script.sh`  
To make a shortcut without into the directory file, you can define a new variable in `.bashrc` file, like this `export PATH="$PATH:~/scripts"`. So you can just call `first_script.sh`

# What is Shebang?
A shebang is a common name for the `#!` notation used in the first line of a script to indicate how it should be run. It's a way to specify the interpreter for a script, particularly in Unix-like operating systems. For example, `#!/bin/bash` would indicate that the script should be run with the Bash shell.  
you can check intrepreter with this `which bash` for bash, and `which python` for pyhton

## Example Shebang in files
1. Bash Language  
``` Shell
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

