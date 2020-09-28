
# Extreme System Design

# Topics to be covered

 1. Loadbalancer
 2. Caching
 
 3. Database
 4. RDBMS design and working
 5. Indexes
    * How indexing works in RDBMS?
 6. ACID vs BASE
 7. Partitioning and Sharding Data
    * Consistent Hashing
    * Strong vs Eventual consistency 
 8. CAP Theorem 
 9. RDBMS vs NoSql
    * Types of NoSQL
      * Key/Value
      * Wide column
      * Document based
      * Graph based
   
# Load Balancer Type

![alt text](https://github.com/JITES/ExtremeSystemDesign/blob/master/LBMindMap.png)


**Load balancer at Networking Layer L4**
Load balance on the packets which you are receiving.

 1. Looks at the IP address and port number and makes the decision on that.
 2. Depending on the algorithm that is defined in the load-balancer software.
 3. Changes the target IP address in the request using Network address translation which happens using the table.
 4. Also incoming IP address is also changed before forwarding to server underneath load-balancer so that server can connect back with the load-balancer 

Pros
 - _Simple load balancing_
 - _Efficient_
 - _More secure ( no need to look into the data )_
 - _One TCP connection_
 - _Network Address Translation_

Cons
 - No smart load balancing
 - NA microservices
 - Sticky per segment
 - No caching `I cant look at the data so cant cache the data`

Eg. LB has IP address and port mapping table, fwd it to corresponding IP:port

**Load balancer at Application Layer L7**
Request is checked against the rules.
Modifies the content and replaces the IP address.
Can look into the data.

Pros -
 - Smart load balancing
 - Caching
 - Great for microservices

Cons
 - Expensive (looks at data)
 - Decrypts (terminates TLS)
 - Two TCP connection

Load balance on http header, decision based on http-header

* Hardware Load balancer
	* Expensive and only giant tech companies uses them 

* Software Load balancer
	 * Algo -
		 * Round robin
		 * Round Robin with weighted server
		 * Least Connections
		 * Least Response Time
		 * Source IP hash
		 * URL hash

# Http routing pattern

 - Host based
 - Path based
 - Header based
 
 
Reference and material

https://landing.google.com/sre/books/

