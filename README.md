# CITS2002 Project 2

Due date: **11:59pm Friday 22nd October (end of week 12)**

Grade Weighting: **25%**

Authors: Dempsey Thompson, Zach Manson

`duplicates` is (will be) a command line utility to locate and report duplicate files in (and below) a named directory based on SHA2 hashes.

## Usage

Compile using command `make` in root directory.

Run `duplicates` TBD.


## Useful Information:

 + Week 8 Lecture 16 (this content I believe is a big part of project)
 
Project info:
 + [project explanation](https://teaching.csse.uwa.edu.au/units/CITS2002/projects/project2.php)
 + [project clarifications](https://teaching.csse.uwa.edu.au/units/CITS2002/projects/project2-clarifications.php)
 + [sample solution output](https://secure.csse.uwa.edu.au/run/duplicates)
 + [submission location](https://secure.csse.uwa.edu.au/run/cssubmit)  (only 1 member needs to submit)

# Todo
 + [ ] plan out program structure
 + [x] figure out how makefiles work
     + [ ] setup make on dempsey's pc computers
 + [x] scan directory
 + [ ] some kind of hashmap?
 + [ ] do flags

## Suggested Plan
 + [x] find a project partner.
 + [ ] Determine what activities are to be performed by the program. 
 + [ ]	Determine what data needs to be stored during the execution of the program. 
 + [ ]	Design one of more data types and data structures to store this long-term data, and create a new duplicates.h header file to define these constructs.
 + [ ] break up the activities into fairly independent sets. Write a number of "empty" C files, each of which includes your `duplicates.h` header file, to implement the activities. Ensure that your file implementing the main() function is named `duplicates.c`.
 + [ ] write a Makefile to compile and link your C files, each of which will be dependent on the header file.
 + [ ] write the main() function, whose initial task is simply to receive and validate the command-line options and arguments. Write a  usage() function to report the program's synopsis, should command-line processing detect any errors.
 + [ ] ensure that the "real" command-line argument is the name of a directory that you can read it.
 + [ ] open and read each directory, locating all regular files in the directory. At this stage (as a debugging aid) just print each filename as it is found. When directories are located within directories, you should process those directories recursively.
 + [ ] add support for the -a command-line option when finding files.
 + [ ] store the name (location) and size of each file found in each directory.
 + [ ] having finished reading the directories, identify all duplicate files.
 + [ ] if the -q command-line option is provided, perform its role and terminate.
 + [ ] if no command-line options are provided, print out the required "statistics" about the files found and terminate.
 + [ ] if the -l command-line option is provided, perform its role and terminate.
 + [ ] armed with a fully tested program, and overflowing with confidence, consider of the advanced tasks (described below).

ADVANCED FEATURES:
 + [ ] support duplicate detection in and below two or more directories provided on the command-line. For example, if four directory names are provided, then all files in all four directories should be considered.
 + [ ] support the presence of hard-links (but not symbolic-links) in the directories being considered. When counting the total number of bytes occupied by all files, the "contents" of all files hard-linked together are counted only once.
 + [ ] support the -m command-line option.
	This task requires you to identify duplicate files and to then store only one instance of each (with possibly different names). The Linux link() system call (see man 2 link) provides this facility for us, by creating hard-links between two or more files. The actual file contents will only be stored only once, and multiple relative pathnames will refer to that single copy.

WARNING: until you are very confident that your duplicates program is working correctly, you are strongly advised NOT to use your duplicates program to use the -m option to minimize the storage of important files and directories!

PROJECT REQUIREMENTS:
 + [ ] Your project must be developed in multiple C11 source files and (at least one) header file.
 + [ ] Your submission will be compiled with the C11 compiler arguments -std=c11 -Wall -Werror -pedantic, and marks will not be awarded if your submission does not compile.
 + [ ] Compilation and linking of your project must be supported by a Makefile, containing approriate variable definitions and automatic variables.
 + [ ] The default target of your Makefile must be named duplicates, and invocation of the make command must produce an executable program named duplicates.
 + [ ] Your project must employ sound programming practices, including the use of meaningful comments, well chosen identifier names; appropriate choice of basic data-structures, data-types, and functions; and appropriate choice of control-flow constructs.
