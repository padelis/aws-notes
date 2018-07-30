## Business Benefits of Cloud.

- Almost zero upfront infra investment.
- Just-in-time Infra.
- More efficient resource utilization.
- Usage-based costing.
- Reduced time to market.

## Technical Benefits of cloud

- Automation - "Scripting Infrastructure"
- Auto-scaling
- Proactive Scaling
- More Efficient Development lifecycle
- Improved Testability
- Distaster Recovery and Business Continuity
- "Overflow" the traffic to the cloud

## Design For Failure

Rule of thumb: Be a pessimist when designing architectures in the cloud, assume things will fail. In other words, always design, implement and deploy for automated recovery from failure.

In particular, assume that your hardware will fail. Assume that outages will occur. By being a pessimist, you end up thinking about recovery strategies during design time, which helps in designing an overall system better.

## Decouple Your Components

The key is to build components, that do not have tight dependencies on each other, so that if one component were to die, sleep or remain busy fro some reason, the other components in the system are built so as to continue to work as if no failure is happening.

In essence, loose coupling isolates the various layers and components of your application so that each component interacts asynchronously with the others and treats them as a "black box"

## Implement Elasticity

1.  Proactive Cyclic Scaling (Periodic scaling - daily weekly)

2.  Proactive Event-based Scaling (e.g Black Friday)

3.  Auto-scaling based on demand
