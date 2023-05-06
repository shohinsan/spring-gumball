# CMPE 172 - Lab #10 Notes

# Steps done to create Spring Gumball CI/CD to GKE

Gradle Dependencies:
1) Spring Web
2) Thymeleaf
3) Spring Boot DevTools
4) Validation
5) Lombok
6) Testcontainers

Paths Configuration:
1) Group: com.example
2) Artifact: spring-gumball:2.2
3) Name: spring-gumball:2.2
4) Package Name: come.example.spring-gumball:2.2
5) Packaging: Jar

# Continuous Integration (CI) Workflow

### 1. CI Workflow Image

![1  CI Workflow](https://user-images.githubusercontent.com/22685770/236644989-110e972c-f113-4cc4-a8a6-514b7a7e8858.png)

### 2. Building and Testing

![2  Building   Testing Java with Gradle](https://user-images.githubusercontent.com/22685770/236645007-5ae4fc09-7e24-4db7-94fb-6e4389ab6dfe.png)

# Continuous Development (CD) Workflow

### 3. Created GKE Cluster

* This step involves creating a Google Kubernetes Engine (GKE) cluster to host the application. This can be done through the Google Cloud Platform Console or the gcloud command-line tool.

![3  Created GKE Cluster](https://user-images.githubusercontent.com/22685770/236645015-f6336cbf-2287-4796-8723-6d0adf93a5bc.png)

### 4. Enabled APIs required for this lab. We do not need all of them here since some of them are for the past labs.

* Enabled APIs required for this lab: In order to deploy the application to GKE, certain APIs need to be enabled such as the Google Kubernetes Engine API, Compute Engine API, Container Registry API, and more.

![4  Enabled APIs to Help Me With Labs](https://user-images.githubusercontent.com/22685770/236645024-3ff2ef38-cd61-479d-b9ba-ef5674a794a8.png)

### 5. Project ID

* Each GCP project has a unique project ID which is used to identify the resources associated with that project.

![5  Project ID](https://user-images.githubusercontent.com/22685770/236645037-fc170407-c8ee-4ff1-a7f7-5cb87ced1115.png)

### 6. Create Service Accounts

* Service accounts are used to provide access to resources and services within a GCP project. In this case, a service account is created to provide access to the GKE cluster.

![6  Create Service Accounts](https://user-images.githubusercontent.com/22685770/236645048-ed977e86-0bb6-4ed3-9ee8-537aa3513218.png)

### 7. IAM Roles Linking to service account for my GKE Cluster

* IAM Roles Linking to service account for my GKE Cluster: IAM roles are used to define the permissions and access control for users, groups, and service accounts within a GCP project. In this step, appropriate IAM roles are assigned to the service account created in step 6 to provide the necessary access for deploying and managing the GKE cluster.

![7  IAM](https://user-images.githubusercontent.com/22685770/236645091-3e200a8e-f434-4c08-af19-d19ae95257ee.png)

### 8. Created JSON Service Keys

* Created JSON Service Keys: Service account keys are used to authenticate with GCP APIs and services. In this step, JSON keys are created for the service account created in step 6.

![8  JSON Service Keys](https://user-images.githubusercontent.com/22685770/236645116-02098ed8-078c-4b17-9ce3-b477dad6d3b4.png)

### 9. Action Secrets Created from GitHub

*  In order to deploy the application using GitHub Actions, secrets need to be created and stored securely in the repository settings.

![9  Action Secrets Created From GitHub](https://user-images.githubusercontent.com/22685770/236645122-119540b1-e405-48eb-9528-965d6702851c.png)

### 10. Required Configurations Set

*  Various configurations are needed for deploying the application to GKE such as the container image name, cluster name, project ID, and more. These configurations are set in the GitHub Actions workflow file.

![10  Uploaded Required Configuration](https://user-images.githubusercontent.com/22685770/236645129-46c4dcdd-5454-4b5c-8228-f7bc01de2a55.png)

### 11. CD has been deployed successfully 

* This step involves triggering the GitHub Actions workflow to deploy the application to GKE. If successful, the application will be deployed and running on the GKE cluster.

![11  CD Running](https://user-images.githubusercontent.com/22685770/236645140-e3fc620a-837e-459c-87df-2a4ca56b978c.png)

### 12. Service Ingress is configured

* Ingress is a Kubernetes resource that allows external traffic to be routed to the appropriate Kubernetes services. In this step, an Ingress resource is created to route traffic to the GKE cluster.

![12  Service Ingress](https://user-images.githubusercontent.com/22685770/236645152-f20bd583-28e4-41d8-8f20-2bc754762a16.png)

### 13. Spring Gumball Running on Load Balancer

* Finally, the application is running on a load balancer that is accessible from the internet. This allows users to access the application from anywhere.

![13  Gumball Running on LB](https://user-images.githubusercontent.com/22685770/236645162-c12fae50-b3da-4e44-8f3b-37c163a59cd2.png)
