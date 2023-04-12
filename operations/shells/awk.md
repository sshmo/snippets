# awk

## Getting started

When you run awk, you specify an awk program that tells awk what to do. The program consists of a series of rules. a rule consists of a pattern followed by an action.

pattern { action }

In an awk rule, either the pattern or the action can be omitted, but not both.
If the pattern is omitted, then the action is performed for every input line.
If the action is omitted, the default action is to print all lines that match the pattern (‘{ print $0 }’).

The awk utility reads the input files one line at a time. For each line, awk tries the patterns of each rule. If several patterns match, then several actions execute in the order in which they appear in the awk program. If no patterns match, then no actions run

awk is a line-oriented language. Each rule’s action has to begin on the same line as the pattern. To have the pattern and action on separate lines, you must use backslash continuation; there is no other option

backslash continuation and comments should not mix. As soon as awk sees the ‘#’ that starts a comment, it ignores everything on the rest of the line

You may use backslash continuation to continue a source line. Lines are automatically continued after a comma, open brace, question mark, colon, ‘||’, ‘&&’, do, and else

[awk manual](https://www.gnu.org/software/gawk/manual/gawk)

## How to Run awk Programs

 Use either ‘awk 'program' files’ or ‘awk -f program-file files’ to run awk.

```bash
awk 'program' input-file1 input-file2 … # One-Shot Throwaway awk Programs
awk -f program-file input-file1 input-file2 …
awk 'program' # awk applies the program to the standard input
```

## Executable awk Programs

``` bash
$ nano advice
    #! /bin/awk -f
    BEGIN { print "Don't Panic!" }
$ chmod +x advice
$ ./advice
-| Don't Panic!

```

## Some Simple Examples

``` bash

# use \47 for using single quote as text
awk 'BEGIN { print "Don\47t Panic!" }' 

# like cat file
awk '{ print }' file 

# searches the input file mail-list for the character string 'li'
awk '/li/ { print $0 }' ./mail-list.txt 

# print every line that is longer than 80 characters:
awk 'length($0) > 80' data

# print the longest input line
awk '{ if (length($0) > max) max = $0 } 
    END { print max }' data

# print the longest input line, converting tabs to spaces
expand data | awk '{ if (x < length($0)) x = length($0) }
                   END { print "maximum line length is " x }' 

# print every line that has at least one field
awk 'NF > 0' data 

# print seven random numbers from 0 to 100, inclusive:
awk 'BEGIN { for (i = 1; i <= 7; i++)
                 print int(101 * rand()) }' 

# print the total number of bytes used by files:
ls -l files | awk '{ x += $5 }
                   END { print "total bytes: " x }'

# print the total number of kilobytes used by files:
ls -l files | awk '{ x += $5 }
   END { print "total K-bytes:", x / 1024 }'

# print a sorted list of the login names of all users:
awk -F: '{ print $1 }' /etc/passwd | sort

# count the lines in a file:
awk 'END { print NR }' data

# print the even-numbered lines in the data file:
awk 'NR % 2 == 0' data

# print the total number of bytes in all the files in the current directory that were last modified in November
ls -l | awk '$6 == "Nov" { sum += $5 }
             END { print sum }'

awk '/This regular expression is too long, so continue it\
 on the next line/ { print $1 }'

# print every line that contains the string ‘12’ or the string ‘21’
 awk '/12/ { print $0 } ; /21/ { print $0 }' data

# pretty print of awk variables
 awk '{printf "%3s|%3d|%3d|%3d|%3s \n", FILENAME, FNR, NR, NF, $0}' data

# print lines between 1 and 6 inclusive
 awk 'NR==1, NR==6 {print $0}' data

# print total nimber of feilds in data
 awk '{sum+=NF} END {print sum}' data

# print last feild in each line
 awk '{print $NF}' data
```

## Running awk and gawk

The way to name the standard input, with all versions of awk, is to use a single, standalone minus sign or dash, ‘-’. For example:

``` bash
some_command | awk -f myprog.awk - 
```

## Regular expressions

A regular expression in awk is enclosed in slashes (‘/’) ans used in patterns

regexp constant: a regexp is enclosed in slashes, such as /foo/

escape sequences:character sequences beginning with a backslash (‘\’) for both string constants and regexp constants

``` bash
# matches, or selects, all input records with the uppercase letter ‘J’ 
awk '$1 ~ /J/' inventory-shipped

# matches, or selects, all input records whose first field does not contain the uppercase letter ‘J’
awk '$1 !~ /J/' inventory-shipped

# \" : A literal double quote (should be used for string constants only)

awk '/pattern1/ && /pattern2/ { print; }' # matches strings that match both pattern1 and pattern2
```
