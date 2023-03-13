# Going Back to Lab Report 3 #

When I did lab report 3, I researched the `grep` command and its options. This time, I'm going to research the `find` command and find some of its useful options that can further the command's efficiency in certain situations.

**The options for this command were all found on these websites: [1](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/), [2](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/), [3](https://www.computerhope.com/unix/ufind.htm)

---

1. -name
The -name option searches for a file or directory that is specified by the text put after -name.

---
```console
$find . -name Algarve-History.txt
      ./written_2/travel_guides/berlitz2/Algarve-History.txt
```

```console
$find . -name ch1.txt            
            ./written_2/non-fiction/OUP/Berk/ch1.txt
      ./written_2/non-fiction/OUP/Abernathy/ch1.txt
      ./written_2/non-fiction/OUP/Rybczynski/ch1.txt
      ./written_2/non-fiction/OUP/Kauffman/ch1.txt
      ./written_2/non-fiction/OUP/Fletcher/ch1.txt

```
