# 42-Piscine-Shell01

## ex01
`FT_USER` is a user-defined variable that contains the username of a user whose groups you want to list and format. `echo $FT_USER` to check what it is set to currently. If it prints nothing, then it means `FT_USER` is not set.

You can `man id` and `man tr` before looking at the solution. 

Method without using `id`:<br>
`groups $FT_USER | tr ' ' ',' | tr -d '\n'`

## ex02
By default, the `find` command uses the `-print` action on all files for which the whole expression is true. Unless another action like `-printf` is specified. `man find` and read how to format the output of `find`.

Or you can use:<br>
`find . -type f -name '*.sh' -exec basename {} .sh \;`

## ex03
`man find` and `man wc`.

`ls -aR` does something similar too but isn't fully correct.

## ex04
Refers to media access control (MAC) a.k.a. Ethernet address. It is a unique identifier assigned to network interfaces for communication on a physical network segment.

`man grep` and `man awk`.

Other options:<br>
`ifconfig -a | sed -rn 's/.*(([a-z0-9]{2}:){5}..).*/\1/p'`<br>
`ifconfig -a | perl -lne '/(([a-z0-9]{2}:){5}..)/ && print $1'`<br>
`LANG_ALL=C ifconfig -a | grep 'ether' | tr -s ' ' '\t' | cut -f 3`<br>

## ex05
Google escape characters.<br>

1. `touch \"\\\?\$\*\'MaRViN\'\*\$\?\\\"`
2. Remember to add the number 42 in your file.

## ex06
`man awk` and look at the special variables.

## ex07
`cat /etc/passwd` gives you the contents of the system user account located in the miscellaneous system configuration folder (et cetera).

Remeber to define what you want `FT_LINE1` and `FT_LINE2` to be.

Hints:<br>
1. Comments start with '#'.
2. Look at the `-F` option for `awk`.
3. `man rev`.
4. `man sort`.
5. `man sed`, see how to use `-n` and `p` together.
6. `man sed`, see how to use the substitution command syntax.

## ex08