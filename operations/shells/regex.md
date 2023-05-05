# Regular Expressions

1. Your task is to match the string hackerrank. This is case sensitive.

    ``` py
    pattern = r'\bhackerrank\b'
    ```

2. you have a test string. Your task is to write a regular expression that matches only and exactly strings of form: abc.efg.hij.klm, where each variable can be any single character except the newline.

    ``` py
    pattern = r'^[^\n]{3}\.[^\n]{3}\.[^\n]{3}\.[^\n]{3}$'
    ```

3. Given a test string, , write a RegEx that matches under the following conditions:
must start with Mr., Mrs., Ms., Dr. or Er..
The rest of the string must contain only one or more English alphabetic letters (upper and lowercase).

    ``` py
    pattern = r'^(?:Mr\.|Mrs\.|MS\.|Dr\.|Er\.)[a-zA-Z]+$'
    ```

4. Your task is to write a regex which will match, with following condition(s):
consists of 8 digits.
may have "-" separator such that string gets divided in parts, with each part having exactly two digits. (Eg. 12-34-56-78).

    ``` py
    pattern = r'^\d{2}(-?)\d{2}\1\d{2}\1\d{2}$'
    ```

5. Write a regex that can match all occurrences of o followed immediately by oo.

    ``` py
    pattern = r'o(?=oo)'
    ```

6. Write a regex which can match all characters which are not immediately followed by that same character.

    ``` py
    pattern = r'(.)(?!\1)'
    ```

7. Write a regex which can match all the occurences of digit which are immediately preceded by odd digit.

    ``` py
    pattern = r'(?<=[13579])\d'
    ```

8. Write a regex which can match all the occurences of characters which are not immediately preceded by vowels (a, e, i, u, o, A, E, I, O, U).

    ``` py
    pattern = r'(?<![aeiouAEIOU]).'
    ```

9. find-substring
Input Format
The first line contains an integer, n, denoting the number of sentences.
Each of the subsequent lines contains a sentence consisting of words separated by non-word characters.
The next line contains an integer, n, denoting the number of queries.
Each line of the subsequent lines contains a string, to check.
Constraints
1 < n < 10
1 < q < 10
Output Format
For each query string, print the total number of times it occurs as a sub-word within all words in all.\

    ```py
    import re
    from typing import List

    n_sent = input()
    n_sent = int(n_sent) if n_sent.isdigit() else 0
    if n_sent:
        sents: List[str] = []
        for i in range(0, n_sent):
            sents.append(input())


    n_query = input()
    n_query = int(n_query) if n_query.isdigit() else 0
    if n_query:
        queries: List[str] = []
        for i in range(0, n_query):
            queries.append(input())

    for query in queries:
        sum: int = 0
        pattern = r"\B" + query + r"\B"

        for sent in sents:
            matchs = re.findall(pattern=pattern, string=sent)
            sum += len(matchs)
        print(sum)

    ```

10. username validation:
    It must begin with either an underscore, "_" (ASCII value ), or a period, . (ASCII value).
    The first character must be immediately followed by one or more digits in the range 0-9 through.
    After some number of digits, there must be zero or more English letters (uppercase and/or lowercase).
    It may be terminated with an optional "_"(ASCII value).
    If it's not terminated with an underscore, then there should be no characters after the sequence of or more English letters.
    If a string is a valid alien username, print VALID on a new line; otherwise, print INVALID.

    * Input Format
    The first line contains a single integer, denoting the number of usernames.
    Each line of the subsequent lines contains a string denoting a username to validate.
    * Constraints
    Iterate through each of the
    If a username is a valid username, print VALID on a new line; otherwise, print INVALID

    ```py
    import re
    from typing import List

    n_user = input()
    n_user = int(n_user) if n_user.isdigit() else 0
    if n_user:
        users: List[str] = []
        for i in range(0, n_user):
            users.append(input())

    pattern = r"^[_.][0-9]+[a-zA-Z]*_?$"
    for user in users:
        if re.findall(pattern, user):
            print("VALID")
        else:
            print("INVALID")

    ```

11. detecting ip
    * Input Format
    An integer N such that N <= 50.
    This is followed by N lines such that each text in each line is either:
        an IPv4 address
        an IPv6 address
        a chunk of text which does not equal either of these.

    * Output Format
    N lines.
    The ith output line should equal (a)IPv4 or (b)IPv6 or (c)Neither depending on what you detected the ith input line to be.

    ```py
    import re
    from typing import List

    n_string = input()
    n_string = int(n_string) if n_string.isdigit() else 0
    if n_string:
        strings: List[str] = []
        for i in range(0, n_string):
            strings.append(input())

    ipv4_pattern = (
        r"^(?:25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[0-9]?[0-9])\."
        r"(?:25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[0-9]?[0-9])\."
        r"(?:25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[0-9]?[0-9])\."
        r"(?:25[0-5]|2[0-4][0-9]|1[0-9][0-9]|[0-9]?[0-9])$"
    )

    ipv6_pattern = (
        r"^(?:0|[0-9a-f]{0,4}):(?:0|[0-9a-f]{0,4}):"
        r"(?:0|[0-9a-f]{0,4}):(?:0|[0-9a-f]{0,4}):"
        r"(?:0|[0-9a-f]{0,4}):(?:0|[0-9a-f]{0,4}):"
        r"(?:0|[0-9a-f]{0,4}):(?:0|[0-9a-f]{0,4})$"
    )

    for string_ip in strings:

        ipv4_matchs = re.findall(ipv4_pattern, string_ip)
        if ipv4_matchs:
            print("IPv4")
        ipv6_matchs = re.findall(ipv6_pattern, string_ip)
        if ipv6_matchs:
            print("IPv6")

        if not (ipv4_matchs or ipv6_matchs):
            print("Neither ")

    ```

12. detecting lattitude and longtitude
    * Input Format
    The first line contains an integer N, which is the number of tests to follow.
    This is followed by N lines of text. Each line contains a pair of co-ordinates which possibly indicate the latitude and longitude of a place.

    * Constraints
    1 <= N <= 100
    The latitude and longitude, if present will always appear in the form of (X, Y) where X and Y are decimal numbers.
    For a valid (latitude, longitude) pair:
    -90<=X<=+90 and -180<=Y<=180.
    They will not contain any symbols for degrees or radians or N/S/E/W. There may or may not be a +/- sign preceding X or Y.
    There will be a space between Y and the comma before it.
    There will be no space between X and the preceding left-bracket, or between Y and the following right-bracket.
    There will be no unnecessary zeros (0) before X or Y.

    * Output Format
    "Valid" where X and Y are the latitude and longitude which you found to be a valid (latitude,longitude) pair.
    If the given pair of numbers are not a valid (latitude,longitude) pair, output "Invalid".

``` py
    import re
    from typing import List

    n_string = input()
    n_string = int(n_string) if n_string.isdigit() else 0
    if n_string:
        strings: List[str] = []
        for i in range(0, n_string):
            strings.append(input())

    pattern = (
        r"\([+-]?(?:90|90\.0+|[1-8]?\d|[1-8]?\d\.\d*),\s"
        r"[+-]?(?:180|180\.0+|1[0-7]\d|1[0-7]\d\.\d+|[1-9]?\d|[1-9]?\d\.\d+)\)"
    )


    for string_ll in strings:

        ll_matchs = re.findall(pattern, string_ll)
        if ll_matchs:
            print("Valid")
        else:
            print("Invalid")

```
