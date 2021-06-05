1. Run a redis instance  
    `docker run --name my-redis-container -p 6379:6379 -d redis:6.2.4`
1. Working without a client (non-SSL)
     ```shell
        $ telnet 6379
        sadd myset "New Item" # Adds a new item to the set 'myset'
        smembers myset # Gets all the members of the 'myset'
        sadd myset "Another Item"
        smembers myset
        scard myset # Gets the number os items in the 'myset'
        quit # Closes this connection
     ```
1. Using redis CLI  
    `$ docker run -it --network <docker-network-of-my-redis-container> --rm redis redis-cli -h my-redis-container`  
    `$ docker run -it --rm redis redis-cli -h my-redis-container`  
### Explore
Redis seems to have simple text based protocol. See below. Need to explore further.  
```shell
$ telnet localhost 6379
sadd myset "Mdone"
:1
sadd myset "etr" "yetyer"
:2
smembers myset
*5
$5
Madhu
$5
Mdone
$3
etr
$4
damn
$6
yetyer
```
