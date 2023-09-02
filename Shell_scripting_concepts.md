# <p align = center > Shell Scripting Concepts </p>

### Shell :
#### <p> The shell is a command-line interface that interprets and executes commands. Common Unix-like shells include Bash,C shell,Zsh, and PowerShell on Windows. <p>
### Commands : 
#### The  commands include cd,pwd,ls,mkdir,rmdir,touch,cat,rm,head,tail,find,kill etc
### Shell Environment:
#### This includes variables, environment variables, and configuration files like .bashrc or .bash_profile, is crucial. These elements affect how your shell scripts behave.
### Input and Output: 
#### Handling standard input (stdin), standard output (stdout), and standard error (stderr). Redirecting, piping, and capturing output from commands are important techniques.
### Conditions and loops:
#### conditional constructs like if, elif, and else to make decisions and control the flow of your script based on conditions.Employing loops such as for and while to perform repetitive tasks, iterate over lists, or process data until certain conditions are met.
### Command-Line Arguments: 
#### Handling command-line arguments passed to scripts using $1, $2, and so on, as well as the special variables like $# and $@.
### Error Handling: 
#### Implementing error trapping, checking exit codes, and logging errors to make scripts more robust.
### Pipes and Filters: 
#### Using pipes (|) to connect commands and filters like grep, sed, and awk to process and transform data streams.
### Exit Codes and Interactive Scripts: 
#### Handling exit codes and using them to determine the success or failure of commands and scripts.Creating scripts that provide interactive command-line interfaces to users, prompting for input and guiding them through tasks.
### Switch cases :
#### Switch cases in shell scripting provide a way to perform different actions based on the value of a variable or an expression. Although the shell script doesn't have a built-in switch statement like some other programming languages,we can achieve similar functionality using case statements within a case/esac block. If none of the conditions match the case then the default case is executed.
### Fail and exit :
#### Shell script exit whenever any command within the script fails, you can use the set -e option. This option tells the shell to exit immediately if any command within the script exits with a non-zero status. We can also add pipefail so that our code gets executed the way it is intended.
### Template Resolution :
#### Template resolution in shell scripting typically refers to the process of substituting placeholders or variables in a template file with actual values. This is a common technique used in various scripting and programming languages to generate dynamic content or configuration files.
#### These placeholders are often denoted by special syntax, such as ${VAR_NAME}. In your shell script, you define the variables and assign values to them. These values are the data you want to replace the placeholders within the template.The shell script reads the template file and processes it line by line. When it encounters a placeholder, it replaces it with the corresponding variable's value.


