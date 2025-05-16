# Secured and Monitored Web Infrastructure

## Infrastructure Diagram

```mermaid
graph TD
    U[User] -->|HTTPS| FW1[Firewall 1]
    FW1 --> LB[Load Balancer HAproxy + SSL]
    
    subgraph Server 1
        FW2[Firewall 2]
        WS1[Web Server: Nginx]
        AS1[Application Server]
        AF1[Application Files]
        MC1[Monitoring Client]
        FW2 --> WS1
        WS1 --> AS1
        AS1 --> AF1
        MC1 -.-> MS[Monitoring Service]
    end
    
    subgraph Server 2
        FW3[Firewall 3]
        WS2[Web Server: Nginx]
        AS2[Application Server]
        AF2[Application Files]
        MC2[Monitoring Client]
        FW3 --> WS2
        WS2 --> AS2
        AS2 --> AF2
        MC2 -.-> MS
    end
    
    subgraph Server 3
        FW4[Firewall 4]
        DB[(MySQL Database)]
        MC3[Monitoring Client]
        FW4 --> DB
        MC3 -.-> MS
    end
    
    LB -->|HTTPS| FW2
    LB -->|HTTPS| FW3
    AS1 --> FW4
    AS2 --> FW4
```

## Infrastructure Explanation

### Additional Security Elements

1. **Firewalls**
   - Control incoming and outgoing traffic
   - Protect servers from unauthorized access
   - Filter malicious traffic
   - Implement security policies

2. **SSL Certificate**
   - Enables HTTPS for encrypted traffic
   - Protects sensitive data in transit
   - Provides authentication and trust
   - Required for secure online transactions

3. **Monitoring Clients**
   - Collect system and application metrics
   - Monitor server health and performance
   - Track resource usage
   - Enable proactive issue detection

### Monitoring Details

1. **Purpose**
   - Track system health and performance
   - Detect and alert on issues
   - Analyze trends and patterns
   - Support capacity planning

2. **Data Collection**
   - Monitoring clients collect metrics
   - System metrics (CPU, memory, disk)
   - Application metrics (response times, errors)
   - Network metrics (bandwidth, latency)
   - Log files and events

3. **QPS Monitoring**
   - Monitor Queries Per Second at web server
   - Set up specific metrics in monitoring tool
   - Create dashboards for visualization
   - Configure alerts for threshold violations

## Infrastructure Issues

1. **SSL Termination at Load Balancer**
   - Traffic between load balancer and servers is unencrypted
   - Internal network vulnerable to attacks
   - Increased security risk within infrastructure

2. **Single Write Database**
   - No database redundancy for writes
   - Single point of failure for write operations
   - Potential data loss or service interruption
   - Limited write scalability

3. **Uniform Server Components**
   - All servers have same components
   - No specialization for specific tasks
   - Resource allocation may be inefficient
   - Harder to optimize for specific workloads
   - Increased maintenance complexity