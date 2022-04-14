# Designing an API Rate Limiter

An API reate limiter will throttle users based on the number of requests they are sending.

## Why Rate Limiting?
Rate limiting helps to protect services against abusive behaviors targeting the application such as Denial-of-service (DOS) attacks, brute-force password attempts, brute-force credit card transactions, etc.

We also want to prevent revenue loss, to reduce infrastructure costs, stop spamming and stop online harassment. 

Here's some scenarios that show how benefitial it is to Rate limit our API/Service:

- **Misbehaving clients:** Sometimes, clients can overwhelm servers by sending large number of requests, either intentionally or unintentionally. 

- **Security:** Limiting the number of times a user is allowed to try authenticating with a wrong password.

- **Preventing abusive and bad design practices:** Without API limits, developers of client apps might request the same info over and over again.

- **Revenue:**  Certain services might want to limit operations based on the tier of their customer's service and thus create a revenue model off the rate limiting. To go beyond the set limit, the user has to buy higher limits.

- Prevent spikiness of traffic so that the service stays reliably up for all.


## 1. Requirements and System Goals

#### Functional requirements
1. Limit the number of requests an entity can send to an API within a time window
2. The user should get an error whenever they cross the defined threshold within a single server or across a set of servers.

#### Non-Functional requirements
1. The system should be highly available, always protecting our API service from external attacks.
2. The rate limiter should NOT introduce substantial latencies affecting the user experience.

## 2. Throttling Types

* ***Hard Throttling*** – Number of API requests cannot exceed the throttle limit

* ***Soft Throttling*** – Set the API request limit to exceed by some percentage. E.g, if the rate-limit = 100 messages/minute, and 10% exceed-limit, our rate limiter will allow up to 110 messages per minute

* ***Dynamic Throttling*** – The number of requests can exceed the limit if the system has some free resources available. 

## 3. Algorithms used for Rate Limiting



