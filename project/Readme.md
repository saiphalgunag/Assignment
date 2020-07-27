
## Pre requisites:

1. Docker run time.
2. Kubernetes cluster 

## Installation:

1. Build the docker image using the Dockerfile.
  cd load_balancer_ip_list
  docker build -t nginx:1.18.0 .
2. Apply the kubernrtes manifest using the command

  kubectl apply -f manifest.yaml

3. You can see the status of the deployments with the below command.

    kubectl get pods sai-test

4. You can access the nginx using http://localhost

5. To get the list of ip address of the containers into a file run the command.

    kubectl get Endpoints sai-test -oyaml > container_ip_list.txt

### High Availability:

For High availability we can run kubernetes worker nodes into two differet regions and have the replicas running in two regions using the node affinity.

### Capacity:

If the load is increased then we can increase the number of container or also increase the resources for a container.
  
