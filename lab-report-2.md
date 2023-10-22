# Part 1

> StringServer.java:

```java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String[] messages = new String[0];

    public String handleRequest(URI url) {
       String path = url.getPath();
       String query = url.getQuery();


       if (path.equals("/add-message")) {
        if (query != null && query.length() >= 3 && query.contains("s=")) {
            this.appendMessages(query.split("=")[1]);
        } else {
            return "Invalid query, the URL must contain an s query.";
        }
       }

       if (messages.length == 0) {
	    return "No messages to display.";
       } else {
	    return this.formatMessages();
       }
    }

    private void appendMessages(String s) {
        String[] newArr = new String[this.messages.length + 1];
        for (int i = 0; i < this.messages.length; i++) {
            newArr[i] = this.messages[i];
        }
        newArr[newArr.length - 1] = s;
        this.messages = newArr;
    }

    private String formatMessages() {
        String list = "";
        for (int i = 0; i < this.messages.length; i++) {
            list += String.format("%d. %s\n", i + 1, this.messages[i]);
        }
        return list;
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

![First use of /add-message](images/add-message-1.png)

The `handleRequest` mathod was called on the `Handler` object passed in as an argument to the `Server.start` method with the url argument being `http://ieng6-203.ucsd.edu:4000/add-message?s=Hello`. Within the `handleRequest` method, the methods `getPath` and `getQuery` were called on the url variable of type `URI`. The 

![Second use of /add-message](images/add-message-2.png)

* Methods called:
  
  * `handleRequest` on the `Handler` class
  * `getPath` on the `url` variable of type `URI`
  * `getQuery` on the `url` variable of type `URI`
  * `length` on the `query` variable of type `String`
  * `contains` on the `query` variable of type `String`
  * 
*
*

# Part 2

![Private key](images/private_key.png)

The key my computer uses to log into ieng6 is held in `C:\Users\saber\.ssh\id_ed25519`. The `id_ed25519.pub` file contains the public key which ieng6 uses to compare with my private key.

![Public key](images/public_key.png)

The `authorized_keys` file in ieng6 contains a list of authorized ssh keys, my public key is in this file.

![Logging onto ieng6](images/ssh.png)

Logging onto ieng6 when my computer is authorized produces this terminal interaction.
