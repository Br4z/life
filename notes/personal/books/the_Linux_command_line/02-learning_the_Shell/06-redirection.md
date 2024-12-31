---
reviewed_on: "2024-12-25"
---

# Redirection

- `cat`: concatenate files.

- `sort`: sort lines of text.

- `uniq`: report or omit repeated lines.

- `grep`: print lines matching a pattern.

- `wc`: print newline, word, and byte counts for each file.

- `head`: output the first part of a file.

- `tail`: output the last part of a file.

- `tee`: read from standard input and write to standard output and files.

## Standard input, output, and error

Keeping with the Unix theme of "everything is a file", programs such as `ls` actually send their results to a special file called **standard output** (often expressed as **stdout**) and their status messages to another file called **standard error** (**stderr**). By default, both standard output and standard error are linked to the screen and not saved into a disk file.

## Redirecting standard output

I/O redirection allows us to redefine where standard output goes. To redirect standard output to another file instead of the screen, we use the `>` redirection operator followed by the name of the file...

```BASH
# <command> > <existing file>

ls -l /usr/bin > ls-output.txt
```

With the command above, we created a long listing of the `/usr/bin` directory and sent the results to the file `ls-output.txt`. Let's set what happens if we wire a wrong directory:

```BASH
ls -l /bin/usr > ls-output.txt

# ls: cannot access /bin/usr: No such file or directory
```

The reason why it displays an error message instead of saving it to the file is because `ls` does not send its error messages to standard output. Instead, like most well-written Unix programs, it sends its error messages to standard error. Because we redirected only standard output and not standard error, the error message was still sent to the screen.

...if we ever need to actually truncate a file (or create a new, empty file), we can use a trick like this:

```BASH
> ls-output.txt
```

If we want to append redirected output to a file instead of overwriting the file from the beginning, we use the `>>` redirection operator.

## Redirecting standard error

Redirecting standard error lacks the ease of a dedicated redirection operator. To redirect to standard error, we must refer to its **file descriptor**. A program can produce output on any of several numbered file streams...

- `0`: standard input.

- `1`: standard output.

- `2`: standard error.

```BASH
# <command> <file stream>> <file name>

ls -l /bin/usr 2> ls-error.txt
```

### Redirecting standard output and standard error to one file

```BASH
# <command> > <file name> 2>&1
# <command> >> <file name> 2>&1
```

> The order of the redirections is significant.

Recent versions of `bash` provide a second, more streamlined method for performing this combined redirection, shown here:

```BASH
# <command> &> <file name>
# <command> &>> <file name>
```

### Disposing of unwanted output

...The system provides a way to do this by redirecting output to a special file called `/dev/null`. This file is a system, often referred to as a **bit bucket**, which accepts input and does nothing with it. To suppress error messages from a command, we do this:

```BASH
# <command> 2> /dev/null
```

## Redirecting standard input

### `cat`

`cat` reads one or more files and copies them to standard output.

```BASH
# cat [file...]
```

---

Because `cat` can accept more than one file as an argument, it can also be used to join files together.

```BASH
# movie.mpeg.001 movie.mpeg.002 ... movie.mpeg.099

cat movie.mpeg.0* > movie.mpeg
```

> Because wildcards always expand in sorted order, the arguments will be arranged in the correct order.

---

If `cat` is not given any arguments, it reads from standard input, and since standard input is, by default, attached to the keyboard, it is waiting for us to type something. If we type something and press `CTRL + d` to tell `cat` that it has reached end of file (EOF) on standard input, it finishes its execution.

> We can use this behavior to create short text files.

---

Let's try redirecting standard input.

```BASH
cat < lazy_dog.txt

# The quick brown fox jumped over the lazy dog.
```

## Pipelines

The capability of commands to read data from standard input and send to standard output is utilized by a shell feature called **pipelines**. Using the **pipe** operator `|`, the standard output of one command can be piped into the standard input of another.

```BASH
# <command> | <command>

ls -l /usr/bin | less
```

### The difference between `>` and `|`

...the redirection operator connects a command with a file, while the pipeline operator connects the output of one command with the input of a second command.

### Filters

```BASH
# <command> | <filters> | <command>
```

...Filters take input, change it somehow, and then output it...

---

```BASH
ls /bin /usr/bin | sort | less
```

The command above is to make a combined list of all the executable programs in `/bin` and `/usr/bin`, put them in sorted order, and view the resulting list.

#### `uniq`

...It accepts a **sorted** list of data from either standard input or a single filename argument and, by default, removes any duplicates from the list...

> It is important that the list is sorted because it only filter **adjacent** matching lines.

```BASH
ls /bin /usr/bin | sort | uniq | less    # See the uniques elements

# ----------------------------------------------------------------------- #

ls /bin /usr/bin | sort | uniq -d | less # See the duplicates elements
```

#### `wc`

It is used to display the number of lines, words, and bytes contained in files.

```BASH
wc ls-output.txt

7902 64566 503634 ls-output.txt
```

In this case, it prints out three numbers: lines, words, and bytes contained in `ls-out put.txt`...The `-l` option limits its output to report only lines. Adding it to a pipeline is a handy way to count things...

```BASH
ls /bin /usr/bin | sort | uniq | wc -l # See the number of items we have in our sorted list
```

#### `grep`

```BASH
grep <pattern> <filename>
```

When `grep` encounters a "pattern" in the file, it prints out the lines containing it...

```BASH
ls /bin /usr/bin | sort | uniq | grep zip # Find all the files in our list of programs that had the word "zip" embedded in the name

# bunzip2
# bzip2
# gunzip
# gzip
# unzip
# zip
# zipcloak
# zipgrep
# zipinfo
# zipnote
# zipsplit
```

There are a couple of handy options for `grep`:

- `-i`: perform the search in a no case sensitive way.

- `-v`: print only those lines that do not match the pattern.

#### `head` and `tail`

The `head` command prints the first $10$ lines of a file, and the `tail` command prints the last $10$ lines.

> The number of lines can be adjusted with the `-n` option.

`tail` has an option that allows you to view the file in real time (`-f`). This is incredibly useful when you are monitoring log files.

> The prompt will not be available until you press `CTRL + c`.

### `tea`

The `tea` program reads standard input and copies it to both standard output (allowing the data to continue down the pipeline) and to one or more files. This is useful for capturing a pipeline's contents at an intermediate stage of processing.

```BASH
ls /usr/bin | tee ls.txt | grep zip

# bunzip2
# bzip2
# gunzip
# gzip
# unzip
# zip
# zipcloak
# zipgrep
# zipinfo
# zipnote
# zipsplit
```
