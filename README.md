```
Consistent Hashing:

The problem with load balancing is adding and removing servers which actually changes the local data present at each server.

To avoid that we can make use of consistent hashing.

We can still hash request ids.

Instead of an array which can map the hash function from 0 to m-1. 
we can make use of a ring of hash.
```

<img width="683" alt="Screenshot 2023-04-27 at 12 29 24 AM" src="https://user-images.githubusercontent.com/43849911/234676103-91338374-da4d-4eb5-b775-1ef1ed43897d.png">


```
Servers themselves have the ids. We can hash the server ids as well using the hash function and take the remainder by search space (m)

Example:
Server 1 position = h(0) % 30 = 49 % 30 = 19

Various servers will be hashed this way.

Whenever request comes in to the ring, we'll go clockwise and find the nearest server.

That server will be serving that request.
```

<img width="850" alt="Screenshot 2023-04-27 at 12 35 07 AM" src="https://user-images.githubusercontent.com/43849911/234677406-a79d41c1-cdc4-4e83-8de4-e3d74cd29094.png">
