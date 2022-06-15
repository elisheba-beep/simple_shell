# Simple Shell

## About
A shell takes commands from the user, gives the operating system to perform and returns an output to the user if necessary.
On most Linux systems, the shell used is called ```bash``` and it was created by Steve Bourne.
This project is modelled after the early Unix shells such as Thompson shell.
When in interactive mode, the program gets a command from the user through the terminal, checks if it's a valid command and executes if it is. The user can also pipe the output from other commands into the shell which makes it work in non-interactive mode.
For more information about the shell, refer to ```man_1_simple-shell```

## Installation
To install our shell on your Linux machine, clone this repository into a fresh directory and compile it with the following command:

    gcc -Wall -Werror -Wextra -pedantic *.c -o hsh
