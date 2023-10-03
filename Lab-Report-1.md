cd with no args
```
[user@sahara ~]$ cd
[user@sahara ~]$ 
```
<br />
cd to a directory

    [user@sahara ~]$ cd lecture1/
    [user@sahara ~/lecture1]$ 

<br />
cd to a file

    [user@sahara ~/lecture1]$ cd Hello.java
    bash: cd: Hello.java: Not a directory

<br />
ls with no args

    [user@sahara ~]$ ls
    lecture1

<br />
ls to a directory

    [user@sahara ~]$ ls lecture1/
    Hello.class  Hello.java  messages  README

<br />
ls to a file

    [user@sahara ~]$ ls Hello.java
    ls: cannot access 'Hello.java': No such file or directory

<br />
cat with no args

    [user@sahara ~]$ cat

<br />
cat to a directory

    [user@sahara ~]$ cat lecture1/
    cat: lecture1/: Is a directory

<br />
cat to a file

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
