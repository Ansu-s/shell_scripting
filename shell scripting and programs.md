# <u><p align = center > Basic Linux Bash Script Commands & Programs <P></U>

### Change directory to a specified path :
cd /path/to/directoryName

### Print the current working directory :
pwd

### List the contents of the current directory :
ls

### Create a new directory :
mkdir new_directory

### Remove a directory (only if it's empty) :
rmdir directory_name

### Create an empty file :
touch fileName.txt

### View the contents of a file :
cat fileName.txt

### Remove a file :
rm fileName.txt

### Display the first few lines of a file :
head fileName.txt

### Display the last few lines of a file :
tail fileName.txt

### Find files or directories matching a pattern :
find /path/to/search -name "pattern"

### Kill a process by its process ID (PID) :
kill process_id which can be obtained from the task manager.

# <U><p align=center>Programs including variables,environment variables and functions</p> </U>

### To tell the compiler to use bash shell:
#!(It is called a shebang mostly treated as a comment by the interpreter) then the location of the compiler /bin/bash

### Declare and use a simple variable :
    name="Ansu"
    echo "Hello, $name!"

### Create and use environment variables :
Environment variables are the Variables that are exported to all processes spawned by the shell. Their settings can be seen with the env command. A subset of environment variables, such as PATH, affects the behavior of the shell itself. Shell (local) variables – Variables that affect only the current shell.

    export MY_VARIABLE="This is an environment variable"
    echo "Environment Variable: $MY_VARIABLE"

### Define a function that uses a parameter :
    show() {
    local greeting="Hello"
    local person_name="Ansu"
    echo "$greeting, $person_name!"
    }

### Call the function with a parameter :
    greet "Ansu"

### Accessing environment variables :
    echo "Home Directory: $HOME"
    echo "User: $USER"

### Using configuration files like .bashrc or .bash_profile :
    echo "Contents of .bashrc:"
    cat ~/.bashrc
    echo "Contents of .bash_profile:"
    cat ~/.bash_profile

## Shell program to demonstrate the input and showing output process :
 
```#!/bin/bash

 echo "Enter your name:"
 read name

echo "Hello, $name!"

echo "Enter a number:"
read num1

echo "Enter the second number:"
read num2

sum=$((num1 + num2))
echo "The sum of $num1 and $num2 is: $sum"

echo "Enter the name of a file:"
read filename

if [ -e "$filename" ]; then
echo "Contents of $filename:"
cat "$filename"
else
echo "File not found: $filename"
fi

echo "This is inserted if the above statement is true using the fi command." > output.txt
echo "Contents have been written to output.txt"
```
## Shell program to demonstrate the condition statements :

```#!/bin/bash

age=25

if [ "$age" -ge 18 ]; then
echo "You are an adult."
else
echo "You are a minor."
fi
 ``` 
## Switch Cases :
````
#!/bin/bash
echo "Choose an option:"
echo "1. Add A"
echo "2. Multiplication B"
echo "3. Division C"
read choice

case $choice in
1)
    echo "You have chosen Option A."
    ;;
2)
    echo "You have chosen Option B."
    ;;
3)
    echo "You have chosen Option C."
    ;;
*)
echo "Invalid choice. Please select a valid option."
;;
esac
````
## Error Handling in Shell :

### Function to handle errors and log them to a file :

    handle_error() {
    local error_message="$1"
    local timestamp=$(date '+%Y-%m-%d %H:%M:%S')
    echo "[$timestamp] ERROR: $error_message" >> error.log
    exit 1
    }

### Trap errors and call the handle_error function :
    trap 'handle_error "An error occurred while running the script"' ERR

### Simulate an error by trying to remove a non-existent file :
    rm non_existent_file.txt

### Check the exit status of the previous command :
    if [ $? -ne 0 ]; then
    handle_error "Failed to remove the file."
    else
    echo "File removed successfully."
    fi

### Another example: dividing by zero :
    echo "Let's divide 10 by 0 and handle the error."
    result=$(echo "scale=2; 10 / 0" | bc 2>&1)

    if [[ "$result" == *"divide by zero"* ]]; then
    handle_error "Division by zero."
    else
    echo "Result: $result"
    fi       

### If no errors occurred, log a success message :
    echo "Script completed successfully." >> error.log

### Pipe and filter :

```` #!/bin/bash
echo "Fruit Data:"
echo "Apple
Banana
Cherry
Date
Elderberry
Fig" > fruits.txt

echo "Original Data:"
cat fruits.txt

echo "Filtering lines containing 'Banana' or 'Cherry':"
cat fruits.txt | grep -E 'Banana|Cherry'

rm fruits.txt
````
### Fail and exit :

```#!/bin/bash
echo "Checking for a network connection..."

ping -c 3 google.com > /dev/null 2>&1

if [ $? -ne 0 ]; then
echo "Error: Unable to establish a network connection."
exit 1
fi

echo "Success: A network connection is available."
```
### Template Resolution :

Here we hava a template file where we can replace the different elements with data.
The below is the template.txt file.

    Hello, {{name}}!
    Today is {{day}}.
If we want to replace the data in above template file we use the below code.

```#!/bin/bash
day=$(date +%A)
template=$(cat template.txt)
template=${template//\{\{name\}\}/Ansu} 
template=${template//\{\{day\}\}/$day}  

echo "$template" > resolved_template.txt
echo "Template resolved and saved to resolved_template.txt"
```






