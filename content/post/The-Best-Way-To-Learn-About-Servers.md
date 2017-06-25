+++
categories = ["Golang", "Server", "http"]
date = "2017-06-18T00:32:18Z"
draft = "false"
title = "The best way to learn about servers"

+++

When I was first starting out in the web world I didn't know anything about tcp, http or how servers worked. I realized rather quickly that this was a huge road block in my development of applications and control of systems.  

I first spent some time trying the most well known servers. Apache, Nginx, Tomcat, IIS.

None of these really gave me a firm understanding of the nuts and bolts of how a server was put together and how to speak tcp/http language.

I decided if I was going to do this, I was going to go all out. I reckoned if I wanted to really understand servers and how they work, I should write my own.

Enter [Golang](https://golang.org/), an open source, general purpose programming language developed by google.

Golang has a rich standard library which includes an http package with which you can build your own http server and host your own website in minutes.

## http server in go

Here is the simplest https server in go taken from the godocs themselves:



```golang

package main

import (
	"io"
	"net/http"
	"log"
)

// hello world, the web server
func HelloServer(w http.ResponseWriter, req *http.Request) {
	io.WriteString(w, "hello, world!\n")
}

func main() {
	http.HandleFunc("/hello", HelloServer)
	log.Fatal(http.ListenAndServe(":12345", nil))
}

```
