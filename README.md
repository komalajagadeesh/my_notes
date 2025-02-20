AWS Zero to Hero 

Day 18: AWS Cost Optimisation Project

AWS Cloud Cost Optimization - Identifying Stale Resources

Identifying Stale EBS Snapshots

In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.
Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.
=======================

-optimise the infra costs.
-understanding how devops engineers can implement CO using delete option ie, by deleting the stale resources.

We will use Lambda function - python code (boto3 module) -it talks to AWS api

ex: you will write Lambda function individually.
Ex: to write for eps snapshots 
Python code written talks to was api and gets complete info of EBS snapshots if there are stale/active snapshots.

-can delete unused/stale snapshots using same lambda functions

-Lambda functions are usually event driven so you can trigger this lambda function using cloud watch.

-Snapshots make sense if it’s available for a volume that’s attached to an Instance.
If not if they are available for a long time and nobody is using it, it’s better to delete them.

-
Lambda functions -> Python -> AWS API s

1. To fetch All the EBS snapshots
2. To filter out the snapsshots which are stale and delete.

-

->for 6months if the snapshot are not used, delete them (advanced) learn later.



