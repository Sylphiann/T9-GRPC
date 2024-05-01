# Module 9 - High Level Networking
Favian Naufal - **2006597802**

## Reflection
1. What are the key differences between unary, server streaming, and bi-directional streaming RPC (Remote Procedure Call) methods, and in what scenarios would each be most suitable?

**Answer**:<br>
In a sense, the key differences between those three methods are in the the amount and the direction of the message are being sent. <br> 
- Unary involves a single request and response, which is enough for any simple communication involving relatively simple and small payload of message, much like fetching a data. <br>
- Server streaming works well when the response sent from the server is large as it sends messages incrementally, as it is a perfect method for retrieving logs from a server in real time. <br>
- Bi-directional streaming, as its name suggests, involves both parties of the communication exchanging messages in real time, it should be easy to imagine how it works within social platform applications, as it implements this method to show two parties sending messages to each other in a private message room.
<br><br>
---
2. What are the potential security considerations involved in implementing a gRPC service in Rust, particularly regarding authentication, authorization, and data encryption?

**Answer**:<br>
Much like what other languages and their frameworks provided, authentication and authorization can also be implemented with JSON Web Tokens, as Rust also provided JWT handling library like `jsonwebtoken`. <br>
This also applies to data encryption, as Rust also provides many data encryption libraries where one can use it to encrypt data before sending it. 
<br><br>

---
3. What are the potential challenges or issues that may arise when handling bidirectional streaming in Rust gRPC, especially in scenarios like chat applications?

**Answer**:<br>
I can only imagine this since I haven't tried this feature much yet. Though this question should be involved with the answer of the previous question, as the security involving the messages sent within a chat application could be an issue. But the harder challenge could be in making sure concurrent streams are being handled well, which might sound harder when doing it in Rust.
<br><br>

---
4. What are the advantages and disadvantages of using the `tokio_stream::wrappers::ReceiverStream` for streaming responses in Rust gRPC services?

**Answer**:<br>
I'm afraid I don't have many idea about this specific module. But if I had to research, this module works as a wrapper around `tokio::sync::mpsc::Receiver` that implements `Stream`, which should work well with Rust's asynchronous ecosystem. as for disadvantages, using this module involves additional overhead and complexity around the process, so it might not be as flexible to support many other features and optimiazions provided by gRPC.
<br><br>

---
5. In what ways could the Rust gRPC code be structured to facilitate code reuse and modularity, promoting maintainability and extensibility over time?

**Answer**:<br>
this should be the same case just like any other language. Code separation into reusable modules, dedicated design patterns, and many other way could be applied in this case.
<br><br>

---
6. In the **MyPaymentService** implementation, what additional steps might be necessary to handle more complex payment processing logic?

**Answer**:<br>
Providing extra data validation, error handling, following the complex payment processing logic should be necessary.
<br><br>

---
7. What impact does the adoption of gRPC as a communication protocol have on the overall architecture and design of distributed systems, particularly in terms of interoperability with other technologies and platforms?

**Answer**:<br>
As I see it in this tutorial, adopting gRPC as a communication protocol proves to be much more efficient compared to how REST API works, looking on the performance of the messages being sent, supported by its reduced overhead. Although I can't confidently say this protocol as a replacement of REST API, at least not yet, as the question mentioned that there should be many other technologies and platforms that isn't compatible with this communication protocol.
<br><br>

---
8. What are the advantages and disadvantages of using HTTP/2, the underlying protocol for gRPC, compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs?

**Answer**:<br>
the main advantage should be on how HTTP/2 handle messages asynchronously, which doesn't work well with HTTP/1.1, as it also provides multiplexing, header compression, and a lot of other features. The disadvantages lies around the complexity involved around HTTP/2, as there are also limited support around HTTP/2 compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs.
<br><br>

---
9. How does the request-response model of REST APIs contrast with the bidirectional streaming capabilities of gRPC in terms of real-time communication and responsiveness?

**Answer**:<br>
REST APIs works relatively simple with a request-response model which doesn't seem to be as efficient to be used for a real-time communication. Which is where bidirectional streaming capabilities of gRPC works well in that regard.
<br><br>

---
10. What are the implications of the schema-based approach of gRPC, using Protocol Buffers, compared to the more flexible, schema-less nature of JSON in REST API payloads?

**Answer**:<br>
I'm not familiar on how schema-based approach of gRPC using Protocol Buffers works. But in my research and observation, protocol buffer uses a strong typing which reduces the risk of data validation errors, which sound like an issue JSON looking at its schema-less nature in its usage within REST API.