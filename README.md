## Features
- Execute any Unix command (ls, pwd, echo, gcc, rm...)
- Built-in cd with ~ expansion and error handling
- Built-in exit
- Graceful handling of EOF (Ctrl+D)
- Error reporting for failed commands and forks

## Build
gcc shell.c -o shell

## Run
./shell

## How It Works

Every command follows this flow:

1. Read input from user
2. Parse into command and arguments
3. Fork a child process
4. Child executes the command via execvp
5. Parent waits for child to finish
6. Repeat

Built-in commands (cd, exit) are handled directly by the shell process without forking, since they need to modify the shell's own state.

## Concepts Demonstrated
- fork() — process creation
- execvp() — program execution
- waitpid() — process synchronisation
- strtok() — input parsing
- getenv() — environment variable access
- chdir() — directory navigation
- fgets() — safe input reading

## Author
Rumit Maharjan
