
# Extreme System Design

# Topics to be covered

 * Loadbalancer
 * Algo
 * Caching
 * Redis

 * Database
 * RDBMS design and working
 * Indexes
    * How indexing works in RDBMS?
 * ACID vs BASE
 * Partitioning and Sharding Data
    * Consistent Hashing
    * Strong vs Eventual consistency 
 * CAP Theorem 
 * RDBMS vs NoSql
    * Types of NoSQL
      * Key/Value
      * Wide column
      * Document based
      * Graph based
   
# Load Balancer Type

**Load balancer at Networking Layer L4**
 Load balance on the packets which you are receiving. 
Eg. LB has IP address and port mapping table, fwd it to corresponding IP:port

**Load balancer at Application Layer L7**
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
