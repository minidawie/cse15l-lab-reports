Code for StringServer

 ```
import java.util.*;
import java.net.URI;
import java.io.IOException;

class Handler implements URLHandler {
    List<String> FullList = new ArrayList<String> ();
    int i = 0;
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("String Server Size: %d", FullList.size());
        } else if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    FullList.add("\n" + (++i) + " " + parameters[1]);
                    String str = FullList.toString().replaceAll(",", "");
                    str = str.substring(1,str.length()-1);
                    return String.format("%s", str);
                }
            return String.format("Strings added.");
        } else {
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```


