# Scheduler Simulator

A simple user-space scheduler written in C. Allows an arbitrary list of programs to be scheduled and executed, implementing signals to ensure only one program is running at any one time.

# Configuration

A configuration file consists of any number of lines in the following format, each specifying a single process to be executed:

```
<priority> <path> <arguments>
```

- Priority is an integer between 0 and 20 (inclusive), where 0 is the highest priority, and 20 the lowest priority.
- path is the path to the program to be executed
- arguments are any command line parameters to be passed to the program

## Example configuration

```
4 /usr/bin/ls $HOME/Downloads
0 /usr/bin/neofetch
9 ./add.sh 3 4
```

# Compilation

To compile the program, a makefile is provided in the `src` directory. To make everything run:

```bash
cd src
make all
```

To then clean generated files, run:

```bash
make clean
```

# Running

Running the generated program can be done by running the following in the `src` directory:

```bash
./sched <config-file>
```

# Testing

Test executables can be found in the `Tests` directory. To compile just the tests run:

```bash
cd src
make tests
```
