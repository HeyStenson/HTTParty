# 🐱🌐💻‼️
## How does the internet give us cat pictures? 

A classic question that web developers love to ask each other is: What happens when you type a web address into your browser's address bar?

When you first hear that question, you're likely to say, "Well, it's simple - you type it in, and then the browser brings it back, and -" and then you start *really thinking* about it, and realize that it's actually a really tricky question!

There are a lot of things in life that we also take for granted without knowing how they work, like starting a car or turning on a light. So why should we have to know how this works when it's not a huge deal whether we know how the other ones work? Think about it this way - if you're a electrician, you need to know what happens when you flip a light switch, and if you're a mechanic, you need to know what happens when you start a car. And you're studying to be a software engineer, so it's important for you to know what happens when we type a web address into the browser! 

This could be a whole class in and of itself, but I want you to come away from this with a good overview of the process. So let's get into it. 

So the first part of this process is you typing an address into the browser bar. Let's say something like `http://www.cutekittens.com/cutest-kitten-of-the-year.html`. This address is actually composed of several different parts, each of which contributes something different to the process. 

First there's `http`. HTTP stands for **H**yper**t**ext **T**ransfer **P**rotocol, and it's used to transmit and receive web pages. HTTP just one of a few protocols that are used for transmitting information from a web server to a client. A client is what's receiving the information - in this case, your browser. There are other protocols you may have seen, like SMPT for mail and FTP for files. When you type "http://" before a website's address, you are telling a web server how to retrieve the document that you want by specifiying the protocol it should use. HTTP is used by your browser to communicate with the web server, telling it to bring you the web page you've requested. 
 
These requests are sent using a URL, a Uniform Resource Locator. The URL contains the protocol, the host's address, and the resource path, so you end up with something that looks like our example from before. 

<table>
	<tr>
		<th>Protocol</th>
		<th>Domain Name</th>
		<th>Top-Level Domain</th>
		<th>Port</th>
		<th>URL Path</th>
	</tr>
	
	<tr>
		<td>http://</td>
		<td>www.cutekittens</td>
		<td>.com</td>
		<td>80</td>
		<td>cutest-kitten-of-the-year.html</td>
	</tr>
</table>

Now that we've discussed HTTP a little bit, let's talk about the domain name, which is the next piece of the puzzle. When you type a website's name into the browser bar, it isn't an actual address for the resources that make up the site. Instead, it's like a code to get to the address! 

**D**omain **N**ame **S**ervers are the secret agent in the middle of the process. They take the human-readable address that you type in, like `cutekittens.com`, and translate it into an IP address, which is the actual address of the resource. IP addresses look something like this: 74.125.236.195, which is a lot harder to remember than a URL! So it's great that we have DNS servers translating for us.   

Wait a second! Top-level domain? Port?! Okay, really quickly: a top-level domain is the suffix at the end of every website address. Common ones are `.com`, `.org`, `.edu`, and `.gov`, while less-common ones are `.cat`, `.wine`, `.gripe` and `.pizza`. And port just refers to the connection that your computer uses to access the internet, and vice versa. The default port is 80, and since that's implied it's just left off of web addresses. 

Finally, we've got the URL path. This is the actual file or resource that's being served, in this case `cutest-kitten-of-the-year.html`. 

So you've used HTTP to make a request to the server, and told it exactly what to look for. If all goes well, the server sends back a response, which includes the resource you requested! 

Like I said before, there's no shortage of things to talk about on this topic, and there's a ton that I'm not covering here. But now you have a good high-level understanding of what happens when you type an address into your browser's address bar! 

--------- 

Demonstrate a basic request/response:

Open terminal and type in `telnet www.google.com 80`
Then you'll be connected! Next, type in 

```
GET / HTTP/1.1
Host: www.google.com
```
You're going to get a really long response with a lot of information. Basically, though, what's just happened is that you've made a request and gotten a response! 