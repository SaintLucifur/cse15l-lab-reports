# Part 1 Search Engine
* Code Block

```
class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String[] list = new String[50];
    int index = 0;

    public String handleRequest(URI url) {
        if(url.getPath().equals("/")) {
            return String.format("Welcome to Lucifer MorningStar's server!" 
            + "\n" + "Try some commands!" + "\n" + "\n" + "/add?s=aNewStringToAdd"
            + "\n" + "/search?s=aStringToSearch");
        }

        else if(url.getPath().contains("/search")) {
            String[] parameters = url.getQuery().split("=");
            String stringsFound = "";
            boolean hasItems = false;
            for(int i = 0; i < list.length; i++) {
                if(list[i] == null) {
                    continue;
                }

                if(list[i].toLowerCase().contains(parameters[1].toLowerCase())) {
                    stringsFound += (list[i] + " ");
                    hasItems = true;
                }
                
            }
            if(hasItems) {
                return stringsFound;
            }

            else {
                return "no such item";
            }
        }
        else {
            System.out.println("Path: " + url.getPath());
            if(url.getPath().contains("/add")) {
                if(index < list.length) {
                    String[] parameters = url.getQuery().split("=");
                    if(parameters[0].equals("s")) {
                        list[index] = parameters[1];
                        index++;
                        return "Successfully added " + "\"" + parameters[1] + "\"";
                    }
                }
                else {
                    return "The Server Is Full...";
                }
            }
        }
        return "404 not found" + "\n" + "Try other commands!" + "\n" 
        + "\n" + "/add?s=aNewStringToAdd"
        + "\n" + "/search?s=aStringToSearch";
    }
}

class SearchEngine {
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
Screenshot 1 (home directory page)

![Image](homeLab3.png)

* Methods Called

1. getPath()

    No argument is put in this method. If the input url changes, this would change as well
    
2. equals()

    "/" is the argument put in this method.

3. format()

    Introduction to the server is the argument as a string to this method

Screenshot 2-4 (/add?s=aStringToAdd)

![Image](add1Lab3.png)

![Image](add2Lab3.png)

![Image](add3Lab3.png)

* Methods Called

1. getPath()

    No argument is put in this method. If the input url changes, this would change as well

2. contains()

    "/add" is the argument to this method

3. getQuery()

    No argument is put in this method. If the input url changes, this would change as well
![Image](searchLab3.png)
![Image](noItemLab3.png)
![Image](invalidLab3.png)

