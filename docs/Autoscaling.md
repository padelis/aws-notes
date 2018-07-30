# AutoScaling Groups

## Placement Groups

- Clustered Placement groups
  - Is a group of instances **within a single availability zone**.
  - Used when **low latency** is required.
  - High traffic use cases.
- Spread Placement groups
  - Each instance is placed on distinct underlying hardware
  - Separate from each other

The names are unique.

AWS recommends **homogenous instances**. You **can't merge** groups.
