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
