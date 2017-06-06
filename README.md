# Microservices-with-JHipster-and-Spring-Boot

## Run with Kubernetes on Bluemix

1. Install [kubectl](https://kubernetes.io/docs/tasks/kubectl/install/), [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

2. To be able to work with the docker daemon, make sure Docker is running

4. Create Docker images of the `blog` and `store` applications:

   ```bash
   mvn package -Pprod docker:build```
    
5. Create `Kubernetes` cluster on Bluemix

5. Run the following commands in the `kubernetes` directory to deploy to Bluemix. 

    ```
    bx login -a https://api.ng.bluemix.net
    bx cs init
    bx cs cluster-config <cluster-name-in-bluemix>
    (Export the variable KUBECONFIG from the output of above command)
    kubectl apply -f registry
    kubectl apply -f blog
    kubectl apply -f store
    ```


