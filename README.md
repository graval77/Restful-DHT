Restful-DHT
A simple peer-to-peer structured overlay network, a distributed hash table (DHT), to be partly deployed into the cloud. This is an implementation of a DHT using REST for communication among nodes. This implementation is done using JAX/RS, specifically using the Jersey implementation of
JAX/RS. Jersey provides some extensions to JAX/RS, particularly for Web service clients, that is used. The nodes of the network will run as standalone Java programs, using an
embedded Grizzly Web server.
Each node has its own “state server.” This state server could be implemented as a singleton RMI object, located in a separate process that functions as a lightweight “database server.” For
simplicity, the server in this case is an in-process singleton object. When an application starts, it creates a state server object and registers it internally. When a Web service request arrives, the
handler for that request looks up the state server in the main program state. Concurrent requests synchronize their accesses to the node’s state using locks in the state server.
