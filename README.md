## Service Discovery

A service registry keeps track of all servers currently running for every service.

1. Whenever a new server of any service comes up, it first registers itself with the service registry.
2. The service registry also needs to send a heartbeat to all the registered services. If a service doesn't respond within a certain time (e.g., 5 seconds), it unregisters that service.

### Service Registry Example Table

| Service Name   | Instance ID       | Host         | Port  | Status    | Last Heartbeat |
|----------------|-------------------|--------------|-------|-----------|----------------|
| user-service   | user-instance-1   | 10.0.1.101   | 8081  | UP        | 30s ago        |
| user-service   | user-instance-2   | 10.0.1.102   | 8081  | UP        | 15s ago        |
| product-service| product-instance-1| 10.0.1.201   | 8082  | UP        | 10s ago        |
| order-service  | order-instance-1  | 10.0.1.301   | 8083  | UP        | 5s ago         |
| order-service  | order-instance-2  | 10.0.1.302   | 8083  | DOWN      | 5min ago       |
| payment-service| payment-instance-1| 10.0.1.401   | 8084  | UP        | 20s ago        |