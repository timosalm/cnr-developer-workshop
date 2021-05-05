Knative Eventing requires one infrastructure prerequisite beyond the Kubernetes cluster and the Cloud Native Runtimes for Tanzu - a message broker. You can use RabbitMQ or an in-memory broker. In a real world environment, an operator would provision a reliable RabbitMQ instance for you, but in this workshop, we'll deploy our own in-memory broker. Run the following in the terminal
```terminal:execute
command: cat << EOF > eventing-broker.yaml
apiVersion: eventing.knative.dev/v1
kind: Broker 
metadata: 
  name: default 
  namespace: cnr-fundamentals-w01-s001
EOF
```