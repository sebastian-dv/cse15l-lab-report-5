# Going Back to Lab Report 3 #

When I did lab report 3, I researched the `grep` command and its options. This time, I'm going to research the `find` command and find some of its useful options that can further the command's efficiency in certain situations. I really liked this lab report because I felt like I learned a lot about how to use the terminal and a lot about options since I would get side tracked looking at other options and how they could be used. I thought it was a lot of fun to finally be able to look at commands and understand what they did since I know what the command itself and the options do. The way I did it during lab report 3 was to simply look up the command, followed by the words "options terminal". I then looked for the commands that seemed the most useful and most applicable to the directory I was working with. I know I would go through each command and try to find a practical use for each of them, the most practical I would write about in the report.

**The options for this command were all found on these websites: [1](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/), [2](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/), [3](https://www.computerhope.com/unix/ufind.htm)**

---

1. -name
The -name option searches for a file or directory that is specified by the text put after -name.

---
```console
$ find . -name Algarve-History.txt
./written_2/travel_guides/berlitz2/Algarve-History.txt
```

```console
$ find . -name ch1.txt            
./written_2/non-fiction/OUP/Berk/ch1.txt
./written_2/non-fiction/OUP/Abernathy/ch1.txt
./written_2/non-fiction/OUP/Rybczynski/ch1.txt
./written_2/non-fiction/OUP/Kauffman/ch1.txt
./written_2/non-fiction/OUP/Fletcher/ch1.txt
```

These commands both search for a file specified by the text written after the option -name. This way, the command will only return the locations of the files or directories which match the text. This is useful when searching through large files with many files when you're only looking for a single or handful of files. This only works if you know the exact name of the file.

2. -type
The -type option allows you to specify what kind of file to search for depending on the letter typed after the option. For example, f (file), d (directory), and more.

---
```console
$ find . -type d
.
./written_2
./written_2/non-fiction
./written_2/non-fiction/OUP
./written_2/non-fiction/OUP/Berk
./written_2/non-fiction/OUP/Abernathy
./written_2/non-fiction/OUP/Rybczynski
./written_2/non-fiction/OUP/Kauffman
./written_2/non-fiction/OUP/Fletcher
./written_2/non-fiction/OUP/Castro
./written_2/travel_guides
./written_2/travel_guides/berlitz1
./written_2/travel_guides/berlitz2

```

```console
$ find . -type f
./.DS_Store
./written_2/non-fiction/.DS_Store
./written_2/non-fiction/OUP/Berk/ch2.txt
./written_2/non-fiction/OUP/Berk/ch1.txt
./written_2/non-fiction/OUP/Berk/CH4.txt
./written_2/non-fiction/OUP/Berk/ch7.txt
```

These commands demonstrate the difference between searching for files and directories, specifically. The first command returns just the locations of directories found within the given directory to search and the second only returned the location of files. The given directory was ".", which just means the current directory. This command is very useful when searching for a specific type of file, there are more types than just files and directories, but we did not learn about those in this class. (The second command's output was shortened because it was extremely long).

3. -delete
This option allows you to delete any files or empty directories that match the parameters given.

---
```console
$ find . -name ch1.txt -delete
```

```console
$ find . -type d -delete
```

When using the -delete option, nothing is printed out after running the command, as shown above. So to confirm that they actually worked I typed the same command and verified that there were no longer any files under the name "ch1.txt", which was true. In one of the previous options, it's clear that there were actually a couple files under that name, but after using the -delete option they no longer exist. The second command did run with no issues, but no directories were deleted. This is because the -delete option can only delete directories which are empty, and none of them were. This option is useful when needing to mass delete files or empty directories. Instead of going through and deleting them one-by-one, one command is all it takes to do the same.

4. -maxdepth [number]
This option allows you to control how deep the find command searches by writing any number after the option.

---
```console
$ find . -maxdepth 2 -type d
.
./written_2
./written_2/non-fiction
./written_2/travel_guides
```

```console
$ find . -maxdepth 3 -type f
./.DS_Store
./written_2/non-fiction/.DS_Store
./written_2/.DS_Store
./written_2/travel_guides/.DS_Store
```

Some directories can have a tremendous amount of files and directories within them, so it can be useful to sometimes only display the files within the chosen directory until a certain depth. Showing all files and directories can be overwhelming at times since it can fill your terminal many times over which can make it hard to find what you were looking for in the first place. If you know that what you're looking for isn't too deep into the chosen directory then using -maxdepth can make it much easier to find it, as seen in the commands above. The first command only shows the directories within the first two depth levels of the current directory. The second command only shows the files within the first three depth levels, which is none because .DS_Store is an invisible file that just stores information about how the file will be viewed, like its icons, and other view options.
