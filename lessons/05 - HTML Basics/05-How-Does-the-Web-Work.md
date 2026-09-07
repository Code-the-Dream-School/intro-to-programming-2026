# How the Web Works

When you open a website, your computer and the server that hosts the site communicate using a set of rules called the client-server model.


- **Client**: Your computer’s web browser (Chrome, Firefox, Safari, etc.).  Your browser's job is to request information, process that information and display it in a way that the user can see and interact with it.

- **Server**: A remote computer that stores the website’s files.
The client asks for resources, and the server provides them.

- **DNS and URLs**: When you type a web address (URL) like https://www.example.com, your browser first contacts a Domain Name System (DNS) server. The DNS acts like the internet’s phone book: it translates the human-friendly address into the IP address of the server.  

- **HTTP/HTTPS**: Once the IP address is known, your browser uses the Hypertext Transfer Protocol (HTTP) or its secure version (HTTPS) to request data.

In simple terms:
- The client says: “Please send me the HTML file for this page.”
- The server replies with the response: “Here’s the file you asked for.”

The server usually sends back three types of files:
- **HTML**: Defines the structure and content of the page.

- **CSS**: Defines how the page should look (layout, colors, fonts).

- **JavaScript**: Defines how the page behaves and responds to actions.

Then, your browser has a rendering engine that:
- Builds the DOM (Document Object Model) from the HTML.

- Applies styles from the CSSOM (CSS Object Model).

- Executes JavaScript using a JavaScript engine (like V8 in Chrome).

Once everything is loaded and running, you can click, scroll, or type, and the JavaScript code listens for those events to make the page interactive.

## In short:

- The client (your browser) makes a request.

- The server responds with files.

- The browser processes HTML, CSS, and JavaScript to render a working webpage.

- JavaScript adds the dynamic, interactive parts.

TBD Add diagram for How the Web Works