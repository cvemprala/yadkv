# yadkv
Yet another distributed key value store

## Aim
The aim is to build a distributed key value store, and as I go along I will try to build a step by step guide on how to build something from scratch.

## Plan
It's been a while since I've been planning to build a key value store. Finally I start, here is how I want to go about building a distributed key value store. Language of choice is [Go][httpx://go.dev]. 

1. **Grasp gRPC Implementation in Go**: The first step is to comprehend the RPC mechanism and then quickly build a service using gRPC in Golang. 
    - Why gRPC? 
      - Imagine you're playing an online multiplayer game. Each player is using a different type of game console (like PlayStation, Xbox, or a PC), but they all need to talk to each other to coordinate during the game. gRPC is like the common language all these consoles speak, so that no matter what type of console they're using, they can understand each other and play together. 
      - Now, let's imagine that you're playing a really, really fast game, where every millisecond counts. You wouldn't want your console to take a long time to send your moves to your friends, right? gRPC is super speedy because it uses a protocol called HTTP/2 and a format called Protocol Buffers, which are designed to send messages quickly and efficiently. 
      - Also, what if you could send and receive several messages at the same time? That'd be cool, right? gRPC can do this too, which helps make everything even faster.
      - Finally, imagine you're playing a secret mission in the game and you don't want anyone else to know your secret game strategies. gRPC has ways to keep your messages secure, so you don't have to worry about others spying on your game plan.
      - So, if you're building a distributed system, which is kind of like a huge, complex online multiplayer game, gRPC can help the different parts talk to each other quickly, efficiently, and securely.


2. **Incorporate Raft Consensus Algorithm**: Raft is a consensus algorithm designed to be more understandable than other protocols. It's used for managing a replicated log and maintaining consistency across nodes in a distributed system. 
    - Want to learn more about Raft?
      - Look at [this](https://thesecretlivesofdata.com/raft/)

3. **Build a Key/Value Store Using Raft**: After setting up Raft, the next move is to build a key-value store on top of it. The key-value store will use Raft's consistency guarantees to ensure that all nodes agree on the stored data.

4. **Implement Sharding**: To enhance the performance of your key-value store, distribute the data among multiple replicated state machines using a technique called sharding. Sharding can significantly increase throughput by allowing different nodes to handle different parts of the data, and hence, different requests concurrently.
