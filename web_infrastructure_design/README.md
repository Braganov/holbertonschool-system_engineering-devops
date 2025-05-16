# Web Infrastructure Design

## Description
This project contains designs for different web infrastructure setups, from a simple web stack to a distributed, secured, and monitored infrastructure. Each design is presented with a detailed diagram using Mermaid and includes comprehensive explanations of components and potential issues.

## Objectives
At the end of this project, you should be able to explain:
- How to draw a diagram covering the web stack
- What each component is doing
- System redundancy concepts
- Acronyms: LAMP, SPOF, QPS

## Files

### [0-simple_web_stack.md](0-simple_web_stack.md)
- One server web infrastructure
- LAMP stack
- Components: Nginx, Application Server, MySQL
- Domain name configuration with www records

### [1-distributed_web_infrastructure.md](1-distributed_web_infrastructure.md)
- Three server web infrastructure
- Load balancer (HAproxy)
- Split components
- Primary-Replica database cluster

### [2-secured_and_monitored_web_infrastructure.md](2-secured_and_monitored_web_infrastructure.md)
- Three server web infrastructure
- Security: SSL certificate, firewalls
- Monitoring: Monitoring clients
- Encrypted traffic
- Performance and health monitoring

### [3-scale_up.md](3-scale_up.md)
- Split components with dedicated servers
- Load balancer cluster
- Enhanced scalability and reliability
- Resource optimization

## Requirements
- Each task includes a diagram made using Mermaid
- All files contain explanations about the infrastructure
- Focus on answering what was asked
- Each task was reviewed by peers during a whiteboarding session

## Concepts Covered
- Web infrastructure design
- Network basics
- Server management
- Load balancing
- Monitoring
- Security
- Scalability
- Database management