1. Component to validate schema for mongodb
    - This should be a service that stands between mongodb and it's client applications
    - If the client's need schema validations they can go through this service to insert or update documents
        - The service then will validate the changes to the documents allowing or denying the modifications.
    - The schema validations should be editable with a GUI
    - Can be implemented with mongoose validators
2. A gateway service that validates requests against schema
    - This service can be used at the public API endpoints
    - Will relieve the individual services from validating the semantics of the request
    - Requests will go through only if these validators allow them
3. Semantic circuit breaker
   1. Opening or closing the circuit on specific parameters in the request. For example, close for write operations.
4. ESB that can deliver service invocations to the right service and publish the results back by calling the call back endpoint. _[Messaging]_ _[Async]_ _[EventDriven]_
   1. For example service A creates the request for service B and habds it over to the ESB
   2. The ESB then takes the request, hits the service B
   3. Once service B gives a response as a message, the ESB calls the response callback of service A with the response message from service B. 
5. Mouse with Finger print scanner
   1. This can be integrated into one of the FIDO authentication provider.
   2. A new authentication provider can be implemented as well.
6. Server MUX
   - When multiple clients ask for the same resource at the same instance, read the resource state once and send it to all the clients
   - In fact, this is where caching comes into picture. 
7. Implement a containerd service server
   - Similar to docker
8. Implement a DevFinOps tool
   - Should support all Cloud service providers
