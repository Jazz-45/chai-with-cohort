
# Getting Started with cURL
## The Server Story

**_==What is a Server?==_**  
In Layman terms Server is a piece of software whose sole purpose is to **serve**. In technical terms, Server is a computer or program that listens for requests made by the client and respons with data,computation or a service. Generally, a client makes a request to the server to perform a specific operation or obtain required data.

_Real-World Example :-_

When we use a weather app and want to see the weather of our city , then the **client** (app on our mobile device) sends a request to a **server** (remote weather database).

**_==Why we need to talk to Server?==_**

We need to talk to the server because most of the heavy real world applications cannot exist on a local device. Moreover, a server can serve many users at a time, but being on a local device restrict it to one. It also acts a centralized data storage for an application and acts as a single source of truth.

## URL

A URL or Uniform Resource Locator or commonly termed as _link_ is a unique address of a specific resource such as webpage, image or document on the internet. It has different parts such as protocol, domain, path, query, etc. Users can access the resource by typing the URL in the address bar of a browser.

## Uncurling cURL

As discussed above that typing the URL in the **browser** helps use to request a server.

But being a developer and to look a bit cool we use cURL (Client URL Transfer).

### cURL

cURL is basically a command-line tool that lets the user to send request a server and see the response without even using a browser. It's a important developer tool that helps to talk to servers and APIs directly from a terminal.

### Why Programmers Need cURL ?

Lets discuss why we actually use cURL :-

- API testing without a Frontend API testing can be done while developing backend before even the frontend exists.
    
- Debugging Network Issues Since we get ==RAW== response from server unlike in Browser, we can inspect headers, cookies and tokens while debugging.
    
- No Dependencies Developers can use cURL from terminal on any OS (Linux, macOS , Windows) with any setup. Can also be used in remote servers which is a everyday job of Backend and DevOps Engineers.
    

And of course it looks very cool :-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769534903077/321fa0ef-e60b-4716-9f6f-7eddab7f52d6.png)

## Hands on with cURL

Let us make our first request using cURL

```bash
curl https://chaicode.com
```

When we execute this command in the terminal we get an HTML response from the website. We get a raw response as mentioned below

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769534798709/ceaefc91-c502-46c9-adf1-bbda65a2deec.png)

This response return RAW HTML webpage in an unrendered fashion unlike browser.The request we just made was a simple HTTP GET request that only returns a simple HTTP response.

## How cURL Talks to APIs

#### GET

GET method is used to request data from a server or API.

```bash
curl https://jsonplaceholder.typicode.com/posts/1
```

#### POST

Post method is used to send/change data to the server or API.

```bash
curl -X POST  https://jsonplaceholder.typicode.com/posts 
-H "Content-Type: application/json" 
-d '{"title":"Hello","body":"First POST","userId":1}'
```

## Common Mistakes in cURL

### Ignoring Status Codes

Beginners looks only at response body. But it is a good practice to check status codes also using the below command.

```bash
curl -i
```

### Forgetting the HTTP Method

Beginner assume that this sends data but the default method is GET here.

```bash
curl https://api.example.com/data
```

### Conclusion

Servers power modern applications by handling requests, managing data, and serving multiple users at scale. URLs identify resources on the web, and tools like **cURL** let developers communicate directly with servers and APIs.













