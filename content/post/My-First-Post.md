+++
categories = ["misc"]
date = "2017-06-18T00:32:18Z"
draft = "false"
title = "My First Post"

+++

This is my first post on the site.  I hope that you like it!

## http server in go

Here is the simplest https server in go to welcome you:


{{< highlight language >}}

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

{{< /highlight >}}
