---
{"dg-publish":true,"permalink":"/learning/programming/python/fast-api/extra-info/common-questions/","dg-note-properties":{"importance":"high","category":"Programming/Python/FastAPI","creation_date":"2026-06-22 10:12","last_modified_date":"Monday 22nd June 2026 10:14:04","status":"🟥","up":["[[FastAPI]]","[[Section 6 - Project 2 - Move Fast with FastAPI]]","[[Extra info]]"],"basedon":null,"course_provider":"udemy","type":"tutorial","created":"2026-06-21T21:42:22-07:00","modified":"2026-06-22T19:14:17+05:30"}}
---

> [!question]- What is an endpoint ? What do you mean when you say an endpoint in fastapi ?
> 
> # What Is an Endpoint in FastAPI?
> 
> An **endpoint** is simply a **URL that your FastAPI application listens to and responds to**.
> 
> Think of an endpoint as a **doorway into your application**.
> 
> When a client (browser, mobile app, Postman, another server, etc.) sends a request to that URL, FastAPI executes the corresponding Python function and returns a response.
> 
> ---
> 
> ## Simple Example
> 
> ```python
> from fastapi import FastAPI
> 
> app = FastAPI()
> 
> @app.get("/books")
> def get_all_books():
>     return books
> ```
> 
> Here:
> 
> ```http
> /books
> ```
> 
> is the **endpoint**.
> 
> And:
> 
> ```python
> def get_all_books():
> ```
> 
> is the code that runs when someone visits that endpoint.
> 
> ---
> 
> ## Visual Representation
> 
> ```text
> Client Request
>       |
>       v
> GET /books
>       |
>       v
> FastAPI Endpoint
>       |
>       v
> get_all_books()
>       |
>       v
> JSON Response
> ```
> 
> ---
> 
> ## Why Is It Called an Endpoint?
> 
> Imagine a road:
> 
> ```text
> Client --------------------> Server
> ```
> 
> The server exposes specific locations where communication can end.
> 
> Those locations are called **endpoints**.
> 
> Examples:
> 
> ```http
> /books
> /books/5
> /books/update_book
> /users
> /users/10
> ```
> 
> Each URL is a different endpoint.
> 
> ---
> 
> # Examples in FastAPI
> 
> ## Endpoint 1
> 
> ```python
> @app.get("/books")
> def get_all_books():
>     ...
> ```
> 
> Endpoint:
> 
> ```http
> /books
> ```
> 
> Purpose:
> 
> ```text
> Return all books
> ```
> 
> ---
> 
> ## Endpoint 2
> 
> ```python
> @app.get("/books/{book_id}")
> def read_book(book_id: int):
>     ...
> ```
> 
> Endpoint pattern:
> 
> ```http
> /books/{book_id}
> ```
> 
> Example request:
> 
> ```http
> /books/5
> ```
> 
> Purpose:
> 
> ```text
> Return book with ID 5
> ```
> 
> ---
> 
> ## Endpoint 3
> 
> ```python
> @app.post("/books/create_book")
> def create_book():
>     ...
> ```
> 
> Endpoint:
> 
> ```http
> /books/create_book
> ```
> 
> Purpose:
> 
> ```text
> Create a new book
> ```
> 
> ---
> 
> ## Endpoint 4
> 
> ```python
> @app.put("/books/update_book")
> def update_book():
>     ...
> ```
> 
> Endpoint:
> 
> ```http
> /books/update_book
> ```
> 
> Purpose:
> 
> ```text
> Update an existing book
> ```
> 
> ---
> 
> # Endpoint = HTTP Method + Path
> 
> Many beginners think the endpoint is only the URL.
> 
> Technically, an endpoint is:
> 
> ```text
> HTTP Method + URL Path
> ```
> 
> For example:
> 
> ```python
> @app.get("/books")
> ```
> 
> and
> 
> ```python
> @app.post("/books")
> ```
> 
> have the same path:
> 
> ```http
> /books
> ```
> 
> but they are **different endpoints** because they use different HTTP methods.
> 
> |Method|Path|Meaning|
> |---|---|---|
> |GET|`/books`|Read books|
> |POST|`/books`|Create book|
> |PUT|`/books`|Update book|
> |DELETE|`/books`|Delete book|
> 
> ---
> 
> ## Real-World Analogy
> 
> Imagine a library building.
> 
> ```text
> Library
> │
> ├── Counter 1 → Borrow Book
> ├── Counter 2 → Return Book
> ├── Counter 3 → Register Member
> └── Counter 4 → Pay Fine
> ```
> 
> The library is your FastAPI application.
> 
> Each counter is an **endpoint**.
> 
> People go to a specific counter depending on what they want to do.
> 
> Similarly:
> 
> ```text
> /books           → Get books
> /books/5         → Get book 5
> /books/create    → Create a book
> /books/update    → Update a book
> ```
> 
> Each endpoint performs a different task.
> 
> ---
> 
> # In Your FastAPI Project
> 
> When you write:
> 
> ```python
> @app.get("/books")
> ```
> 
> you are telling FastAPI:
> 
> > "Create an endpoint at `/books` that responds to GET requests."
> 
> When you write:
> 
> ```python
> @app.put("/books/update_book")
> ```
> 
> you are telling FastAPI:
> 
> > "Create an endpoint at `/books/update_book` that responds to PUT requests."
> 
> ---
> 
> > [!tip]  
> > **Endpoint = A URL in your API where a client can send a request and receive a response.**
> > 
> > In FastAPI, an endpoint is created using decorators such as:
> > 
> > ```python
> > @app.get(...)
> > @app.post(...)
> > @app.put(...)
> > @app.delete(...)
> > ```
> 
> 🎯 **Key Takeaway**
> 
> When you see:
> 
> ```python
> @app.get("/books")
> ```
> 
> Think:
> 
> ```text
> Endpoint:
> GET /books
> 
> Function:
> get_all_books()
> 
> Purpose:
> Return all books
> ```
> 
> The endpoint is the **public address of your API functionality**, while the Python function contains the logic that executes when that endpoint is called.


> [!question]- When running `http://127.0.0.1:8000/docs#/default/get_all_books_books_get` in the browser i get:</br> <PRE><CODE></br>WARNING:  StatReload detected changes in 'books.py'. Reloading...</br>INFO:     Started server process [511691]</br>INFO:     Waiting for application startup.</br>INFO:     Application startup complete.</br>INFO:     127.0.0.1:34508 - "GET /docs HTTP/1.1" 200 OK</br>INFO:     127.0.0.1:34508 - "GET /openapi.json HTTP/1.1" 200 OK</br>INFO:     127.0.0.1:42324 - "GET /books?status_code=200 HTTP/1.1" 200 OK</br></CODE></PRE></br>I guess 8000 in `http://127.0.0.1:8000/docs#/default/get_all_books_books_get` means port 8000 is open on the server and it is listening for requests coming on its 8000 port, but what about all the above different ports showing in the response `127.0.0.1:34508`, `127.0.0.1:42324` and so on ?
Yes. `8000` is the **server port** where Uvicorn/FastAPI is listening.
> 
> ```text
> http://127.0.0.1:8000/docs
>           │       │
>           │       └── server port
>           └── server IP address
> ```
> 
> The ports in the logs are different because they are **client-side temporary ports**.
> 
> Example:
> 
> ```text
> 127.0.0.1:34508 - "GET /docs HTTP/1.1" 200 OK
> 127.0.0.1:42324 - "GET /books?status_code=200 HTTP/1.1" 200 OK
> ```
> 
> Here:
> 
> ```text
> 127.0.0.1:34508
> 127.0.0.1:42324
> ```
> 
> means the **browser/client** used temporary local ports `34508` and `42324` to connect to the FastAPI server.
> 
> So the full connection looks like this:
> 
> ```text
> Browser/client                FastAPI server
> 127.0.0.1:34508  ───────▶     127.0.0.1:8000
> 127.0.0.1:42324  ───────▶     127.0.0.1:8000
> ```
> 
> `34508` and `42324` are called **ephemeral ports**. Your operating system automatically assigns them for outgoing client connections.
> 
> 📌 Important distinction:
> 
> ```text
> 127.0.0.1:8000   = server listening port
> 127.0.0.1:34508  = browser's temporary client port
> 127.0.0.1:42324  = browser's temporary client port
> ```
> 
> Also, this log line:
> 
> ```text
> GET /books?status_code=200
> ```
> 
> suggests `status_code=200` is being sent as a **query parameter** to `/books`, probably from Swagger UI. It is not the HTTP response status code. The actual response status code is the final:
> 
> ```text
> 200 OK
> ```