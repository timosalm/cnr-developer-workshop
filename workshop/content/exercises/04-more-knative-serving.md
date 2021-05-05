Let's take a look at some more tasks we can accomplish using Cloud Native Runtimes for Tanzu and the "kn" CLI.

To interact with the service we just deployed, we'll use "kn service update". To get an overview of the operations you can perform, try 
```terminal:execute
command: kn service update --help
```

**Set Scaling Limits**
You can set the minimum and maximum number of replicas of your application using the "--scale-min" and "--scale-max" parameters to "kn service update". CNR will autoscale the number of replicas of your application between these two limits based on the number of concurrent requests that your application is receiving.

Try setting minimum and maximum scale by running
```terminal:execute
command: kn service update helloworld-go --scale-min 1 --scale-max 5
```

You can disable either scaling limit by setting it to 0. To revert the limits set above, run
```terminal:execute
command: kn service update helloworld-go --scale-min 0 --scale-max 0
```

**Set Resource Requirement Requests**
You can set resource requests for your application using the "--request" parameter to "kn service update". Try setting a request by doing
```terminal:execute
command: kn service update helloworld-go --request "cpu=100m,memory=512Mi"
```

You can unset requests you've made previously by appending a "-" to the resource name in your request. Try removing the CPU request you just set by doing
```terminal:execute
command: kn service update helloworld-go --request "cpu-"
```
