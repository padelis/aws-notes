# Simple Workflow Service

Amazon Simple Workflow Service is a web service that makes easy to coordinate work across distributed applications

- Media processing
- Business process workflows
- Analytics pipelines

Task represent invocations of processing steps (application code, human actions) in an application

## SWF Workflow Starters

Initiate the workflows.

## SWF Workers

Programs that interact with Amazon SWF to get tasks, process received tasks and return results

## SWF Decider

Programs that control the coordination of tasks, i.e their ordering, concurrency and scheduling according to the application logic.

## SWF Workers & Deciders

Can run on EC2 instances or on machines behind firewalls. SWF brokers the interactions between them. It allows the decider to get consistent views into the progress of task and initiate new tasks.

At the same time, SWF also stores tasks, assigns them to workers and monitor their progress. **It ensures that a task is assigned only once.**

This is the main different with SQS - Task are assigned **only once** with SWF.

SWF maintains application state. Workers and deciders can **run independently and scale quickly**.

## SWF Domains

Workflow and activity types are scoped to a domain. Domains isolate a set of types, executions and task lists from others within the same account.

```
https://swf.us-east-1.amazonaws.com
RegisterDomain
{
  name: "13132",
  description: "This domain is so important",
  workflowExecutionRetentionPeriodInDays: "60"  
}
```

Maximum Workflow Duration is **1 year**

## SQS vs SWF

SQS represents a **message oriented API**
SWF represents a **task oriented API**

SWF ensures that a task is **assigned only once**.
With SQS you have to handle duplicate messages

SWF keeps tracks of all tasks and events
With SQS you need to implement your own application-level tracking.
