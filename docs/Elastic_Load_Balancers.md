# Elastic Load Balancers

Application Load Balancers

- best suited for HTTP/HTTPS
- Operate at layer 7
- advanced routing requests

Network Load Balancers

- best suited for TCP
- Operate at layer 4
- millions request - low latency

Classic Load Balancers

- best suited for HTTP/HTTPS & TCP
- Operate at layer 4 and 7
- sticky sessions

504 is gateway timeout the application is not working?

X-Forwarded-For headers (public ip)
where the users are coming from

Point a domain name to load Balancer's DNS name and put E2C instances behind it.

Instances monitored are

- InService
- OutofService

Only DNS names NO IP address

ELB FAQ Must read.
