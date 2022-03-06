# API Gateway
#cloud distributed #decoupling #microservices #architectural

[source](https://java-design-patterns.com/patterns/api-gateway/) 

## Intent
The API Gateway is a single location where all the calls to microservices are aggregated to. The user makes a single call to the API Gateway, 
and the API Gateway then calls each revelant microservices. 

## Explanation  
A client may need data from multiple different microservices. If the client called each microservice directla, tht could contribute to longer load times,
since the client would have to make a network request for each microservice called. If would also tie the client to each microservice, if the internal implementations of the microservice change (e.g. two microservices are combined in the future) or if the location (host and port) of a microservice changes, then every client that makes use of those microservices must be updated.

The intent of the API Gateway pattern is to alleviate some of these issues. In the API Gateway pattern, an additional entity (the API Gateway) is placed between the client and the microservices. The job of the API Gateway is to aggregate the calls to the microservices. Rather than the client calling each microservice individually, the client calls the API Gateway a single time. The API Gateway then calls each of the microservices that the client needs.

**Real world example**   
We are implementing microservices and API Gateway pattern for an e-commerce site. In this system the API Gatewa makes calls to the Image and Price microservices.

**In plain words**   
For a system implemented using microservices architecture, API Gateway is the single entry point that aggregates the calls to the individual microservices.

**Wikipedia says**   
API Gateway is a server that acts as API front-end, receives API requests, enforces throttling and security polices, passes requests to the back-end service and then passes the response back to the requester. A gateway often includes a transformation engine to orchestrate and modify the requests and responses on the fly. A gateway can also provide functionality such as collecting analytics data and providing caching. The gateway can provide functionality to support authentication, authorization, security, audit and regulatory compliance.

**Programmatic Example - stored under the current directory**
