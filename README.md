# 🐱🌐💻‼️
## How does the internet give us cat pictures? 

A classic question that software engineers, web developers, and other cool people love to ask each other is: What happens when you type a web address into your browser's address bar?

When you first hear that question, you're likely to say, "Well, it's simple - you type it in, and then the browser brings it back, and -" and then you start *really thinking* about it, and realize that it's actually a really tricky question!

![mind=blown](https://media.giphy.com/media/vjyl3YVgcLiWA/giphy.gif)

There are a lot of things in life that we also take for granted without knowing how they work, like starting a car or turning on a light. So why should we have to know how this works when it's not a huge deal whether we know how the other ones work? Think about it this way - if you're a electrician, you need to know what happens when you flip a light switch, and if you're a mechanic, you need to know what happens when you start a car. And you're studying to be a software engineer, so it's important for you to know what happens when we type a web address into the browser! 

This could be a hours-long lecture instead of a little talk, but I want you to come away from this with a good overview of the process. 

The first part of this process is you typing in the browser bar. Let's say something like `http://cutekittens.com/cutest-kitten-of-the-year.html`. This is a URL, or a Uniform Resource Locator, and it's essentially the address for the resource that you're requesting. Just like a physical address is actually composed of many different parts, like a house number, a street name, a city, a state, and a zip code, a URL is composed of several different parts, each of which contributes something different to the process of retrieving the resource. 

These parts are the _protocol_, the host's _domain name_ and _top-level domain_, a _port_ number, and the _resource path_, so you end up with something that looks like our example from before. The table below shows that breakdown:

<table>
	<tr>
		<th>Protocol</th>
		<th>Domain Name</th>
		<th>Top-Level Domain</th>
		<th>Port</th>
		<th>Resource Path</th>
	</tr>
	
	<tr>
		<td>http://</td>
		<td>cutekittens</td>
		<td>.com</td>
		<td>80</td>
		<td>cutest-kitten-of-the-year.html</td>
	</tr>
</table>

First there's `http`. HTTP stands for **H**yper**t**ext **T**ransfer **P**rotocol, and it's used to transmit and receive web pages. HTTP just one of a few protocols that are used for transmitting information from a web server to a client. A client is what's receiving the information - in this case, your browser. The other protocols include SMPT for mail and FTP for files. When you type "http://" before a website's address, you are telling a web server how to retrieve the resource that you want by specifiying the protocol it should use. 

Now let's talk about the domain name, which is the next piece of the puzzle. When you type a website's name into the browser bar, it isn't an actual address for the resources that make up the site. Instead, it's like a code to get to the address! **D**omain **N**ame **S**ervers are the secret agent in the middle of the process. They take the human-readable address that you type in, like `cutekittens.com`, and translate it into an IP address, which is the actual address of the server that the resource lives in. IP addresses are a string of numbers like 74.125.236.195, which is a lot harder to remember! So it's great that we have DNS servers translating for us. 

Next up, we've got the top-level domain. A top-level domain is the suffix at the end of every website address. Common ones are `.com`, `.org`, `.edu`, and `.gov`, while less-common ones are `.cat`, `.wine`, `.gripe` and `.pizza`. 

The port just refers to the connection that your computer uses to access the internet, and vice versa. The default port is 80, and since that's implied it's just left off of web addresses. That's why you hardly ever see a port specified in web addresses, and when you do it's not 80.

Finally, we've got the resource path. This is the actual file or resource that's being served, in this case `cutest-kitten-of-the-year.html`. But something like `pretty-kitty.jpg` would also be a totally valid resource path, as would `cats-of-the-world.pdf`. The client can request, and the server can send, different file types depending on what's been specified in the HTTP request's headers. 

So you've used HTTP to make a request to the server, and told it exactly what to look for. The server sends back a response, which, if everything has gone correctly, includes the resource you requested! Let's take a look at this cycle with a quick demonstration.

--------- 

Open your terminal and type in `telnet www.google.com 80`
Then you'll be connected to the server for www.google.com on port 80. 

If you tried to make a request in English, you'd get a big error code that looks like this:

![Imgur](http://i.imgur.com/sQ5Iyrw.png)

That doesn't work! In fact, you can see that it returns a status code: `400 Bad Request`. Instead, paste in the following code:

```
GET / HTTP/1.1
Host: www.google.com
```

Then hit enter twice. You're going to get a really long response with a lot of information. Basically, though, what's just happened is that you've made a request to GET the requested page using the HTTP/1.1 protocol, and gotten a response! Take a look at the response - you'll see a lot of interesting entries. These key-value pairs are HTTP headers, and they contain a lot of information about what's being returned and how it's being sent. Take a look at the status code for this: `200 OK`.

![Imgur](http://i.imgur.com/9wXWFGJ.png)

--------------

###To recap:

When you type a web address into your browser's address bar, you're actually starting a complex request/response cycle. The URL that you type in starts with a protocol, HTTP, that tells the server how to transmit the resource you want. The domain name of the site is sent through a Domain Name Server, which resolves it into an IP address that maps to a server where the resource is housed. Once your browser has the IP address, it uses that and the port number, usually 80, to connect with the server by sending a request. The server will respond, and if all went well it will return the requested resource to the client, your browser!

Like I said before, there's no shortage of things to talk about on this topic, and there's a ton that I'm not covering here. But now you have a good high-level understanding of what happens when you type an address into your browser's address bar! 

### Further Reading:
[How the Web Works: A Primer for Newcomers to Web Development](https://medium.freecodecamp.com/how-the-web-works-a-primer-for-newcomers-to-web-development-or-anyone-really-b4584e63585c#.a7xwf21oc)

[HTTP Response Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Response_codes)

[HTTP Methods](http://www.tutorialspoint.com/http/http_methods.htm)

![cat typing](https://media.giphy.com/media/LHZyixOnHwDDy/giphy.gif)