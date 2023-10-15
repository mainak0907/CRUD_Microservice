# CRUD_Microservice
Made with Go and Reddis

# Chi

## Install 

```bash
go get -u github.com/go-chi/chi/v5

```

## Introduction

<p>
Chi is a lightweight, fast, and highly flexible multiplexer (or router) for building HTTP services and APIs in the Go programming language. It is an external package in Go and is often used as an alternative to the built-in net/http package's ServeMux for routing and middleware handling. Chi provides a set of features and capabilities for building robust and efficient HTTP services. Some key features and characteristics of Chi include:


### Lightweight and Fast: Chi is designed to be lightweight and high-performance. It's optimized for minimal overhead and can route requests quickly.

### Modular and Extensible: Chi is highly modular, allowing developers to compose and customize their routers and middleware easily. It supports middleware chaining and flexible routing patterns.

### Context Handling: Chi uses a context package for managing request-specific data and values, making it easy to pass data between middleware and request handlers.

### Param Handling: Chi provides a convenient and powerful mechanism for handling URL parameters, such as route segments and query parameters.

### Middleware: Chi supports middleware for tasks like authentication, logging, and request/response manipulation. Middleware can be easily added to routes and applied in a specific order.

### Routing: Chi provides powerful routing capabilities, supporting complex route patterns, route groups, and subrouters.

### Clean API Design: Chi's API is designed to be clear and intuitive, making it easy for developers to understand and work with.
</p>


Example -

```bash
package main

import (
    "net/http"
    "github.com/go-chi/chi"
)

func main() {
    r := chi.NewRouter()

    r.Get("/", func(w http.ResponseWriter, r *http.Request) {
        w.Write([]byte("Welcome to Chi!"))
    })

    r.Get("/hello/{name}", func(w http.ResponseWriter, r *http.Request) {
        name := chi.URLParam(r, "name")
        w.Write([]byte("Hello, " + name + "!"))
    })

    http.ListenAndServe(":8080", r)
}


```
