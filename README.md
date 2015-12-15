# Practice 2015 - 03: Encrypted Messages

## Background
Like all comic book bad guys, members of HYDRA are not all that smart. Using
simple encryption techniques, S.H.I.E.L.D. can obfuscate their messages by
reversing parts of them within double quotations so that HYDRA is not able to
comprehend them at all. S.H.I.E.L.D. needs your help to encode these messages,
using the algorithm described here.

We are interested in reversing a string; however, there are some constraints to
the reversal process.

For one, substrings which are within double quotation marks
(i.e. surrounded by the " character) must not be reversed – in other words,
these quoted substrings must remain in place. Additionally, substrings within
double quotation marks which are already inside quoted substrings must be
reversed the same way we would reverse a string originally.

Let us consider some sample cases to illustrate the details of the process:
- 123456 → 654321 – since there are no quotes, this string is reversed the
    standard way
- 12"34"56 → 65"34"21 – the “34” substring remains in place due to the quotes,
    but the remaining string (i.e. what remains after taking out that substring)
    is reversed
- 12"34"56"78"9 → 92"34"65"78"1 – the "34"56"78" substring remains mostly in
    place, with the exception of the “56” substring of that substring, which is
    reversed as if it was an instance of the original problem. The remaining
    part of the string (composed of the 1st, 2nd, and 9th characters) is
    also reversed.

Note that for the last example, it was assumed that the outermost and
innermost pairs of double quotation marks were the ones that
matched (i.e. the quote opened to the left of 3 was closed by the quote to the
right of 8, and the quote opened to the left of 5 was closed to by the quote to
the right of 6). You may assume in general that this pattern holds true – in
other words, the first and last double quotation marks in an input string will
always match each other, and within a properly quoted substring the first and
last double quotation marks will also always match each other.

Also note that a substring within quotes may be empty, and that the entire
input string may be within quotes.

## Description

### Input
The first line of the file will have an integer, n, which is the number of
test cases in this file.

The next n lines will each contain a string to be reversed, as described above.
Any string will be on a single line of length no greater than 255 characters.
Each character of that string is either an alphanumeric character or the
double quotation mark.

Each string will have at most 250 total characters, and at most 50 quotation
marks. All quotation marks will be balanced (i.e. there will never be an odd
number of quotation marks).

### Output
Each string is printed reversed, according to the description above,
on it’s own line.

## Sample
### Input
```
3
uvahspc
co"din"g""is"f"un
she"sells"seashells"by"the"seashore"
```

### Output
```
cpshavu
nu"din"s""ig"f"oc
ehs"sells"ehtsllehs"by"aes"seashore"
```
