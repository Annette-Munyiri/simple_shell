# shellie - Simple Shell
  This is a simple UNIX command line interpreter(CLI) coded for the ALX SE program.
##  Description
  **Shellie** is a simple UNIX command language interpreter coded in C programming language that reads commands from either a file or standard input and executes them.
## Running Shellie
  To invoke shellie, compile all .c files in the repository and run the resulting executable:
  ```
  gcc -Wall -Werror -pedantic -std=gnu89 *.c -o shellie
  ./shellie
  ```
## Environment
  Upon invocation, shellie receives and copies the environment of the parent process in which it's executed. The environment is an array of name-value strings describing variables in the format NAME=VALUE.

## Command Execution
  After receiving a command, shellie tokenizes it into words using " " as a delimiter. The first word is considered the command and all remaining words are considered arguments to that command. Shellie proceeds with the following actions:
  1. If the first character of the command is neither a slash (`\`) nor dot (`.`), the shell searches for it in the list of shell builtins. If there exists a builtin by that name, the builtin is invoked.
  2. If the first character of the command is none of a slash (`\`), dot (`.`), nor builtin, **shellie** searches each element of the **PATH** environmental variable for a directory containing an executable file by that name.
  3. If the first character of the command is a slash (`\`) or dot (`.`) or either of the above searches was successful, the shell executes the named program with any remaining given arguments in a separate execution environment.

## Exiting Shellie
  **Shellie** returns the exit status of the last command executed, with zero indicating success and non-zero indicating failure.
  If a command is not found, the return status is 127; if a command is found but is not executable, the return status is 126.
  All builtins return zero on success and one or two on incorrect usage (indicated by a corresponding error message).

## Authors
  * Eche Peter  <[trustc0de](https://github.com/trustc0de)>
  * Munyiri Annette <[Annette-Munyiri](https://github.com/Annette-Munyiri)>
