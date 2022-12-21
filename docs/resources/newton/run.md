#Queuing system

Newton has a PBS Torque queueing system. To run your codes you have to submit your code using the queueing system.
Please do not run any code directly for this will cause disruption to other users. 
A code that is run directly will be executed on the login node.

In Newton there are the following queues available:

| Queue name   |  Max time | Max number of nodes| Max number of jobs |
|:-------------|----------:|-------------------:|-------------------:|
|   test       |     15:00 |      1             |        1           |
|   standard   |  12:00:00 |     32             |        8           |
|   long       |  48:00:00 |      4             |        1           |

#Submitting a job

To submityour job you can use the command

```
qsub ....
```

Once submitted you can check the status of your job using the command:

```
qstat ...
```

#Interactive session
For testing purposes it might be useful to work in the interactive mode. To do so you can use the command


