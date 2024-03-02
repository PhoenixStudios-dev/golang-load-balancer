# Golang Load Balancer
Project of a Load Balancer in Golang

A load balancer is a device responsible for distributing network traffic among a certain number of servers. Its a fundamental piece to increase reliability and robustness of modern applications

this software offers basic load balancing capabilities to efficiently distribute network traffic among multiple servers. It's designed to be lightweight and easy to use, making it ideal for small to medium-scale applications.

The input is given through a configuration file refered to as `config.yaml`,  example of a configuration file down below:

```yaml
## Load Balancer Port
lb_port: 3000
## Retry limit of a backend server 
retry_limit: 3
## Backend servers host
backends:
  - "http://localhost:8000"
  - "http://localhost:8001"
  - "..."
```

This load balancer supports two strategies:
- Round Robin: this algorithm equally distributes incoming traffic among the available servers
- Least Connections: traffic is distributed taking into account the number of active connections in each server

The strategy con be specified in the configuration file:

```yaml
lb_port: 3000
## LB strategy (uses round-robin as default)
## - round-robin
## - least-connection
strategy: least-connection
retry_limit: 3
backends:
  - "http://localhost:8000"
  - "http://localhost:8001"
  - "..."
```
## References

- [simplelb](https://github.com/kasvith/simplelb) repository project
- [Goconcurrency](https://gist.github.com/rushilgupta/228dfdf379121cb9426d5e90d34c5b96) gist
