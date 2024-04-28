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
