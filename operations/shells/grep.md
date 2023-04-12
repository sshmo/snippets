# grep

Given one or more patterns, grep searches input files for matches to the patterns. When it finds a match in a line, it copies the line to standard output (by default), or produces whatever other sort of output you have requested with options.

Typically patterns should be quoted when grep is used in a shell command.

Newlines within patterns separate each pattern from the next.

``` sh
    grep [option...] [patterns] [file...]
    grep -v # or --invert-match Invert the sense of matching, to select non-matching lines. 
    grep -c # or --count Suppress normal output; instead print a count of matching lines for each input file. 
    grep -m num # or --max-count=num Stop after the first num selected lines.
    gerp -n # or --line-number Prefix each line of output with the 1-based line number within its input file.
    grep -P '^(?=.*pattern1)(?=.*pattern2)' # matches strings that match both pattern1 and pattern
    grep 'pattern1' | grep 'pattern2' # matches strings that match both pattern1 and pattern2
    grep 'pattern1' file_1 | grep 'pattern2' # matches strings that match both pattern1 and pattern2 in file_1

```

[grep manual](https://www.gnu.org/software/grep/manual/grep)
