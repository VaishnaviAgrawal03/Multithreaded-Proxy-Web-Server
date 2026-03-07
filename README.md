Multithreaded Proxy Web Server

A high-performance multithreaded HTTP proxy server implemented in C using socket programming. The server handles multiple client requests concurrently using POSIX threads, integrates thread synchronization mechanisms, and improves response time with a time-based LRU caching system.

This project demonstrates practical concepts of computer networks, concurrency, memory management, and system-level programming.

Features

Handles 100+ concurrent HTTP client requests using multithreading

Built using low-level TCP socket programming in C

Implements thread synchronization using:

Mutex locks

Semaphores

Custom memory management for efficient request handling

Time-based LRU cache to store frequently accessed responses

Improves response time by up to 5× through parallel request processing

Supports standard HTTP GET requests

System Architecture
Client Request
      |
      v
Proxy Server (Multithreaded)
      |
      |---- Thread Pool
      |        |
      |        v
      |   Request Handler
      |
      |---- Cache Manager (LRU)
      |
      v
Remote Web Server
      |
      v
Response -> Cache -> Client
Tech Stack

Language: C

Networking: TCP Socket Programming

Concurrency: POSIX Threads (pthreads)

Synchronization: Mutex Locks, Semaphores

Caching: Time-based LRU Cache

Operating System: Linux / Unix

How It Works

The proxy server listens for incoming client HTTP requests.

Each request is handled by a separate thread to allow concurrent processing.

The server checks whether the requested resource exists in the LRU cache.

If present:

The cached response is returned immediately.

If not:

The request is forwarded to the target web server.

The response is returned to the client and stored in the cache.

Thread synchronization ensures safe concurrent access to shared cache memory.
