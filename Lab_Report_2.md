# Lab Report 2

## Part 1- Implementation of the web server
Using the example from [Week 2 Lab guideline](https://ucsd-cse15l-w23.github.io/week/week2/),
1. Create Interface URLHandler whose input is an URL and interacts with the text of a web page.  

    <pre><code>interface URLHandler {
    String handleRequest(URI url);
    }</code></pre>
    
2. Creat Class Server to listen for incoming connections.
    <pre><code>public class Server {
    public static void start(int port, URLHandler handler) throws IOException {
        HttpServer server = HttpServer.create(new InetSocketAddress(port), 0);

        //create request entrypoint
        server.createContext("/", new ServerHttpHandler(handler));

        //start the server
        server.start();
        System.out.println("Server Started! Visit http://localhost:" + port + " to visit.");
      }
    }</code></pre>
    
3. In SearchEngine.java  

    <pre><code>import java.io.IOException;
    import java.net.URI;


    class Handler implements URLHandler {
        // Create a string list for incoming strings
        String[] stringList = new String[100];
        //the index of a string
        int num = 0;
        // Initiate a string for concatenation
        String connectedString = "";

        // Concatenate strings
        String connectString(String string) {
            connectedString = connectedString + string + String.format("\n");
            return connectedString;
        }

        // To pocess the incoming strings
        public String handleRequest(URI url) {
            if (url.getPath().equals("/")) {
                return String.format("The strings are %s \n", connectedString);
            } else {
                System.out.println("Path: " + url.getPath());
                if (url.getPath().contains("/add")) {
                    String[] parameters = url.getQuery().split("=");
                    if (parameters[0].equals("s")) {
                        connectedString = connectString(parameters[1]);
                        num++;
                        return String.format("The strings are: %s ", connectedString);
                    }
                }
                return "404 Not Found!";
            }

        }
    }

    // Run the web server
    class SearchEngine {
        public static void main(String[] args) throws IOException {
            if (args.length == 0) {
                System.out.println("Missing port number! Try any number between 1024 to 49151");
                return;
            }

            int port = Integer.parseInt(args[0]);

            Server.start(port, new Handler());
        }

    }</code></pre>

4. Compile and run: type `javac Server.java SearchEngine.java` and `java SearchEngine 4000` in the terminal. `4000` is just one of the port. The number could be between 1024 to 49151.
5. Visit http://localhost:4000 on a browser  
<div align = center><img width="600" alt="image" src="https://user-images.githubusercontent.com/57138953/215358652-55d3bafd-f112-4f48-99ad-008d19edb1f1.png"></div>

6. Visit http://localhost:4000/add?s=Hello,%20my%20name%20is%20Brian. on a browser  
<div align = center><img width="600" alt="image" src="https://user-images.githubusercontent.com/57138953/215359224-d853f6a5-664a-41e4-803e-72b06e7b5484.png"></div>

7. Visit http://localhost:4000/add?s=How%20are%20you? on a browser.  
<div align = center><img width="600" alt="image" src="https://user-images.githubusercontent.com/57138953/215359283-e8073dac-97bc-4283-87ee-1d415c0e89cf.png"></div>

8. Traces of program in Step 6 and 7.  
- method called: `handleRequest`, `connectString`
- respective relveant argumets: `URI url`, `String string`

    | field name | Value after 6. | Value after 7. |
    | :-----:| :----: | :----: |
    | url.getpath() | /add?s=Hello,%20my%20name%20is%20Brian. | /add?s=How%20are%20you?|
    | parameters | {s, Hello,%20my%20name%20is%20Brian.} | {s, How%20are%20you?} |
    | connectedString | Hello,%20my%20name%20is%20Brian.\n | Hello,%20my%20name%20is%20Brian.\nHow%20are%20you? |
    
## Part 2- Bugs
What's the bug:























