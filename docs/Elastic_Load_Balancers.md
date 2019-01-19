# Elastic Load Balancers

## Application Load Balancers

- Best suited for HTTP/HTTPS
- Operate at Layer 7
- advanced routing requests

## Network Load Balancers

- Best suited for TCP
- Operate at Layer 4
- Millions request - **Low Latency**

## Classic Load Balancers

- Best suited for HTTP/HTTPS & TCP
- Operate at layer 4 and 7
- Sticky sessions

## ELB Facts

- 504 HTTP Response Code is a Gateway Timeout (The application is not working for sure).
- X-Forwarded-For headers contain users Public IPs
- Point a Domain Name to Load Balancer's DNS name and put E2C instances behind it.
- Instances monitored are **InService** or **OutofService**

[Elastic Load Balancers FAQs here.](https://aws.amazon.com/elasticloadbalancing/faqs/)

## ELB Monitoring

- CloudWatch Metrics
- Access Logs (Disabled by default)
- Request Tracing (**Only for ALB**)
- CloudTrail Logs
