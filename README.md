# Simple Shell

## About
A shell takes commands from the user, gives the operating system to perform and returns an output to the user if necessary.
On most Linux systems, the shell used is called ```bash``` and it was created by Steve Bourne.
This project is modelled after the early Unix shells such as Thompson shell.
When in interactive mode, the program gets a command from the user through the terminal, checks if it's a valid command and executes if it is. The user can also pipe the output from other commands into the shell which makes it work in non-interactive mode.
For more information about the shell, refer to ```man_1_simple-shell```

## Requirements
- All files will be compiled on Ubuntu 20.04 LTS using gcc, using the options -Wall -Werror -Wextra -pedantic -std=gnu89
- A README.md file at the root of the folder of the project
- The code uses Betty coding style
- An AUTHORS file at the root of the repository
- Header files are include guarded

## Installation
To install our shell on your Linux machine, clone this repository into a fresh directory and compile it with the following command:

    gcc -Wall -Werror -Wextra -pedantic *.c -o hsh


## Contents

| File | Function |Description|
|--|--|--|
|**shell.h**|| *libraries, function prototypes, externals, and struct declarations*
|**shell.c**||
||main|	*directs shell through its fundamental loop of parsing and executing commands*
||receive_sig|*prints prompt after user has interrupted loop with "ctrl+c"*
|**_getline.c**|||
||_getline|*reads input stream into buffer and parses into distinct command lines*
||check_buffer|*checks if read buffer is empty*
||copy_buffer|*copies from read buffer up to newline or null-byte*
||shift_buffer|*shifts read buffer contents left n bytes*
|**_strtok.c**||
||_strtok| *separates tab or space-delimited "words" from the command line into an array of distinct tokens*
||count_tokens| *counts the number of tokens in a command line*
||token_length| *takes the length of a given token in a command line*
|**executor.c**||
||exec_mngr|*directs a tokenized command line to either built-in or external execution*
||exec_builtin|*identify and execute a built-in command*
||exec_external|*execute a command-specified external program*
|**get_path.c**||
||get_path|*retrieve path values from the "PATH" environment variable*
||path_check|*determine if argument includes a path*
||path_count|*count number of paths listed in "PATH" variable*
||path_len|*take the length of a path*
|**err_mngr.c**||
||print_err|*format and print error message according to error number*
||case_three|*format error message in case erring built-in function*
|**builtin_exit.c**||
||builtin_exit|*allows user to exit the shell with or without arguments*
||_atoi|*converts number string to an integer*
||is_num|*determines if a string is a number*
|**builtin_env.c**||
||builtin_env|*prints the environment*
|**builtin_cd.c**||
||builtin_cd|*parse arguments to determine and call appropriate cd behavior*
||cd_HOME|*change current directory to home directory*
||cd_current|*change current directory to current directory*
||cd_prev|*change current directory to previous directory*
||cd_parent|*change current directory to parent directory*
|**cd_help.c**||
||cd_arg|*change current directory to path provided as argument*
||cd_user|*change current directory to user home directory*
||get_target| *copy path from an environment variable*
||set_PWD|*set the "PWD" environment variable*
||set_OLDPWD| *set the "OLDPWD" environment variable*
|**mem_help.c**||
||alloc_mngr|*direct dynamic memory allocations and store a pointer to each in linked list for eventual freeing*
||add_mem_node|*add node with pointer to new memory allocation to linked list
||free_mem_list|*free linked list of memory allocations*
||_realloc|*dynamically reallocate memory*
||_memset|*initialize n bytes of memory to designated value*
|**mem_help_2.c**||
||free_static_mem_list|*free linked list of memory allocations*
|**str_help.c**||
||_strlen|*take the length of a string*
||_strncpy|*copy n bytes from one string to another*
||_strcmp|*compare two strings*
||_strncmp|*compare n bytes of two strings*
||_strcat|*concatenate one string to another*
|**str_help_2.c**||
||_revstr|*reverse a string*
|**num_help.c**||
||_itoa|*convert integer to string number*
||count_digit|*count digits in number string*


## Testing
#### Interactive Mode Test

    user$ ./hsh
    $ ls
    a.out file0 file1 test.txt
    $ 
    $ exit
    user$ 

#### Non-Interactive Mode

    user$ echo "ls" | ./hsh
    a.out file0 file1 test.txt
    user$ 

## Authors
- Ayomide Hassan | [@hassanayo](https://github.com/hassanayo)
- Oluwatomiwa Ekwunife | [@elisheba-beep](https://github/elisheba-beep)