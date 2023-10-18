`cd` with no args
```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
- The working directory is `/home/`
- The reason this was the output is because `cd` is used to change directory. If there are no arguments with `cd` then nothing should happen.
- This output is not an error.
  
<br />

`cd` to a directory

    [user@sahara ~]$ cd lecture1/
    [user@sahara ~/lecture1]$ 

- The working directory is `/home/`
- Since the path from the working directory to the directory I was changing to exists, the command `cd` was able to change into `./lecture1`.
- This output is not an error.
  
<br />

`cd` to a file

    [user@sahara ~/lecture1]$ cd Hello.java
    bash: cd: Hello.java: Not a directory

- The working directory is `/home/lecture1/`
- The reason I got this output is because `cd` literally means change directory but Hello.java is a file, not a directory. Since it is not a directory `cd` is not able to change into it.
- This output is not an error.
  
<br />

`ls` with no args

    [user@sahara ~]$ ls
    lecture1

- The working directory is `/home/`
- `ls` is used to list the files and folders in a path. Since lecture1 is the only file in the working directory it was the only thing that was listed.
- This output is not an error.
  
<br />

`ls` in a directory

    [user@sahara ~]$ ls lecture1/
    Hello.class  Hello.java  messages  README

- The working directory is `/home/`
- I used `ls` on the relative path for lecture1 because I wanted to use a different directory than the example above. Since lecture1 contains four files/folders those are what was listed when ls was used.
- This output is not an error.
  
<br />

`ls` to a file

    [user@sahara ~/lecture1]$ ls ./Hello.java
    ./Hello.java

- The working directory is `/home/lecture1/`
- I used `ls` on the file Hello.java and was given back my argument.
- This is not an error.`ls` is used to list the files and folders that are inside the current path. Since there is nothing to expand and list within a file, the input was returned.
  
<br />

`cat` with no args

    [user@sahara ~]$ cat

- The working directory is `/home/`
- When I used `cat` with no arguments the program broke. I believe that this is an error.
- This is an error because these commands should not break edstems terminal.
  
<br />

`cat` in a directory

    [user@sahara ~]$ cat lecture1/
    cat: lecture1/: Is a directory

- The working directory is `/home/`
- When I tried to use `cat` to a directory it returned with a statement because there is nothing to print out from a directory.
- The command that was given was an error. 'cat' is used to show a files content. Since the argument given was a directory and not a file, the terminal ran into an error. The way the terminal handled the error is by returning a message stating that the argument is a directory, not a file.
  
<br />

`cat` to a file

    [user@sahara ~]$ cat lecture1/Hello.java
    import java.io.IOException;
    import java.nio.charset.StandardCharsets;
    import java.nio.file.Files;
    import java.nio.file.Path;

    public class Hello {
      public static void main(String[] args) throws IOException {
        String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
        System.out.println(content);
      }
    }

  - The working directory is `/home/`
  - I got this output because I `cat` to the relative path of Hello.java. When I use the command it is attempted to print out whatever is in the file, in this case the code in Hello.java was printed out.
  - This is not an error.
