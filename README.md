# Bash Cheat Sheet

## Shebang

```bash
#! /bin/bash
```
## Variables

```bash
NAME="name"
echo $NAME
```

## Arguments

```bash
echo $1
```

## User input w/prompt

```bash
read -p "Please input variable" variablename
```

## Control flow

### If

For conditions with numbers:

```bash
if [$2 -lt 21]; then
	...
else
	...
fi 
```

Other operators:

```
-e filename exists
-d filename exists and is a directory
-f filename exists and is a regular file
-s filename exists and its size is greater than zero
-L filename exists and is a symlink
etc...
```

For conditions with strings:

```bash
if [[ "$1" == "lorem ipsum" ]]; then
	...
fi
```

Other operators for strings:

```
=,== compare for equality
!=   different from
<    less than
>    more than
-z   string is empty
-n   string is not empty
```

### Switch

```bash
case $yn in
	 [Yy]*) break;;
	 [Nn]*) exit;;
	 *) echo "Please answer 'y' or 'n'";
esac
```

## Loops

### While

```bash
while true; do
	...
done
```

### For

The general format is:

```bash
for var in RANGE; do
	...
done
```

Some examples below:

```bash
for s in Bash Cheat Sheet; do
	echo $s
done
```

Output:
```bash

Bash
Cheat
Sheet
```

```bash
for i in {0..3}; do
	echo $i
done
```

Output:

```bash
0
1
2
3
```

Ranges also take an "increment" parameter, which will generate a list with every n-th element:

```bash

for i in {0..10..2}; do
	echo $i
done
```

We can also loop over an array:


```bash
ARR=('first' 'second' 'third')
for element in "${ARR[@]}"; do
	echo $element
done
```

