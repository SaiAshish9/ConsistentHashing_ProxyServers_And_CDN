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

Hence, one server can serve multiple requests depending upon the circular position.

For example, S1 can have a load of 2 requests.

Since the hashes are uniform, requests will be uniformed and the load as well.
```

<img width="850" alt="Screenshot 2023-04-27 at 12 35 07 AM" src="https://user-images.githubusercontent.com/43849911/234677406-a79d41c1-cdc4-4e83-8de4-e3d74cd29094.png">

<img width="828" alt="Screenshot 2023-04-27 at 12 38 17 AM" src="https://user-images.githubusercontent.com/43849911/234678114-d0b6283e-8486-451d-97d0-7bc2d1d9f82c.png">

```
Load Factor on an average turns out to be 1/N on average (expected).
```


```
If we've a new server, any req coming there will be served by that server. Earlier that was served by the next nearest server.

Change in the servers load will be much lesser than what was there previously.

Lets say s1 goes down , next server will serve the s1's requests. All of the servers will be served by s4.

We'll have half of the load on a single server.

We can have multiple hash functions to solve this.

If we choose the k effectively, we can entirely remove the load on one of the service.

As load is expected to be distributed uniformly.
```

<img width="859" alt="Screenshot 2023-04-27 at 12 43 13 AM" src="https://user-images.githubusercontent.com/43849911/234679174-c93669d6-0596-42c5-b753-c078b2d21c9e.png">

<img width="984" alt="Screenshot 2023-04-27 at 12 51 57 AM" src="https://user-images.githubusercontent.com/43849911/234681044-e0f82e09-dee2-46ca-ad96-b6bfef32e5fd.png">

```
Consistent Hashing is used by web caches, databases, and effective load balancing. 
```

```
CDNs

https://www.youtube.com/watch?v=8zX0rue2Hic
```

```
Whenever the user needs to connect to the server, it hits the server and asks for the HTML page.
```

<img width="1107" alt="Screenshot 2023-04-27 at 2 42 12 AM" src="https://user-images.githubusercontent.com/43849911/234703853-5fd9296d-e0e6-47e3-9fa8-94fb45ff413a.png">


