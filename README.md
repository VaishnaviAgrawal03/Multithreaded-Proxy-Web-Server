# Multithreaded Proxy Web Server

A high-performance **multithreaded HTTP proxy server** implemented in **C using TCP socket programming**. The server efficiently handles multiple client requests concurrently using **POSIX threads**, integrates **thread synchronization mechanisms**, and improves response time using a **time-based LRU caching system**.

This project demonstrates key concepts of **computer networks, concurrency, caching systems, and system-level programming**.

---

## 🚀 Features

- Handles **100+ concurrent HTTP client requests**
- Built using **low-level TCP socket programming in C**
- **Multithreaded architecture** using POSIX threads
- Thread synchronization with **mutex locks and semaphores**
- **Custom memory management** for efficient request processing
- **Time-based LRU cache** for faster response delivery
- Achieves **up to 5× faster response time** via parallel request handling
- Supports standard **HTTP GET requests**

---

## 🧠 System Architecture

Client Request
      |
      v
Proxy Server (Multithreaded)
      |
      |---- Thread Handler
      |        |
      |        v
      |   Request Processing
      |
      |---- Cache Manager (LRU)
      |
      v
Remote Web Server
      |
      v
Response -> Cache -> Client


---

## 🛠 Tech Stack

| Technology | Usage |
|------------|------|
| C | Core implementation |
| TCP Sockets | Network communication |
| POSIX Threads (pthreads) | Multithreading |
| Mutex Locks | Thread synchronization |
| Semaphores | Resource management |
| LRU Cache | Performance optimization |

---

## ⚙️ How It Works

1. The proxy server listens for **incoming HTTP requests** from clients.
2. Each request is assigned to a **separate thread**.
3. The server checks whether the requested resource exists in the **LRU cache**.
4. If the resource exists:
   - The cached response is returned immediately.
5. If the resource does not exist:
   - The request is forwarded to the **target web server**.
   - The server receives the response and forwards it to the client.
   - The response is stored in the **cache for future requests**.
6. **Mutex locks and semaphores ensure thread-safe access** to shared resources.

---

## 📂 Project Structure


Multi-Threaded-proxy-server
│
├── proxy_server.c
├── cache.c
├── cache.h
├── Makefile
└── README.md


--
https://github.com/Jahanvi021
