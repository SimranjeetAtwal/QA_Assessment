# AccuKnox_QA : Practical Assessment

# Prerequisites
1.	Install either Docker desktop or Podman.
2.	Install Chocolatey for installing minikube.
3.	Clone the git repository.

  	git clone https://github.com/Vengatesh-m/qa-test.git


**Kubernetes Deployment:**

Deploy the services to a local Kubernetes cluster (e.g., Minikube or Kind).

STEP 1: Install Minikube using chocolatey
                
                choco minikube install -y

STEP 2: Create a local minikube cluster.
                
                minikube start --driver=podman
                minikube status

**NOTE : minikube status command is used to check the status of the created cluster. For e.g:**

               $ minikube status
                 minikube
                 type: Control Plane
                 host: Running
                 kubelet: Running
                 apiserver: Running
                 kubeconfig: Configured


STEP 3: Deploy the kubernetes services which are in Deployment folder of the above repository. Follow the below mentioned command:
          
          $ kubectl apply -f ./Deployment/
            deployment.apps/backend-deployment created
            service/backend-service created
            deployment.apps/frontend-deployment created
            service/frontend-service created



**Verification:**

- Ensure the frontend service can successfully communicate with the backend service.
- Verify that accessing the frontend URL displays the greeting message fetched from the backend.

  Follow the below command to check the communication between frontend and backend.

  **STEP 1**: Execute the below command to get the URL :
          minikube service frontend-service –url
          ![image](https://github.com/user-attachments/assets/206eb946-aa3f-4ebe-ac77-7546a4bf45ff)

  **STEP 2**: Check the above output URL in a browser if it displays the backend messege as below:<br>
         <br> ![image](https://github.com/user-attachments/assets/5ac8ae38-e61d-4d1b-aa3a-8564c897a2a6)

  **STEP 3**: Check if the URL displays the greeting message fetched from the backend.

          simra@Simranjeet MINGW64 ~
          $ curl http://127.0.0.1:59516/
            <h1>Hello from the Backend!</h1>



**Automated Testing:**

- Write a simple test script (using a tool of your choice) to verify the integration between the frontend and backend services.
- The test should check that the frontend correctly displays the message returned by the backend.

**Documentation:**

- Provide a README file with instructions on how to set up and run the automated tests script.

**Deliverables:**
- Test script for automated testing.
- README file with setup and execution instructions.

**Github repo should be Public**
