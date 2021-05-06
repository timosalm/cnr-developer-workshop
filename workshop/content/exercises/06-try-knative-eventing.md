Knative Eventing requires one infrastructure prerequisite beyond the Kubernetes cluster and the Cloud Native Runtimes for Tanzu - a message broker. You can use RabbitMQ or an in-memory broker. In a real world environment, an operator would provision a reliable RabbitMQ instance for you, but in this workshop, we'll deploy our own in-memory broker. Run the following in the terminal
```terminal:execute
command: kubectl create -f /opt/workshop/setup/eventing-broker.yaml -n ${SESSION_NAMESPACE}
```
