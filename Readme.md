
# Itinera Project

  

## Overview

  

Itinera is a robust application that helps users find and review businesses, and business users manage their profiles. It's built on a Microservices Architecture using Docker and Kubernetes to ensure independent development and deployment. The frontend uses React and connects with five separate backend microservices, each managing a different functionality.

  

## Frontend - Itinera

  

The frontend is designed with React. It allows two types of users: Business Users and Simple Users.

  

### Features

  

1.  **Business Users**:

- Sign Up and Sign In

- Add and Edit their business description

- Upload business photos

- View, search, and review other businesses

  

2.  **Simple Users**:

- Sign Up and Sign In

- Search for businesses

- Add reviews and upload photos in the reviews for businesses

  

## Backend

  

The backend is composed of five microservices, each handling a unique functionality. Four of them are developed using Spring, and one is developed with Django. The use of different technologies demonstrates the independence and autonomy of the microservices.

  

1.  **Search Microservice**: Handles the functionality of searching for businesses.

2.  **Profile Microservice**: Manages the profiles of the users.

3.  **Review Microservice**: Manages the reviews by the users.

4.  **Ranking Microservice**: Generates a ranking of businesses based on user reviews. This service is developed using Django.

5.  **Photos Microservice**: Manages all the photo-related operations.

  

Each of these services runs in its Docker container. There is one database for each backend, also encapsulated in Docker containers.

  

## Docker & Kubernetes

  

Each backend and database are packed in Docker containers to create an isolated environment. These containers are orchestrated using Kubernetes, which manages all the Kubernetes deployments for each backend.

  

Each deployment can have more than one ReplicaSet, providing redundancy and high availability. In case one of the instances fails, Kubernetes will start a new one instantly. This also helps to handle the load balancing between the instances.

  

The endpoints of the services are managed by Kubernetes Service, which acts as a gateway to access the backend deployments.

  

## Helm

  

We use Helm, a package manager for Kubernetes, to bundle services together. In our project, the Ranking and Review services are part of the same Packaged Business Capability (PBC). This ensures that these two tightly coupled functionalities are developed, managed, and deployed together.

  

## Running the Project


### Clone repository

```bash
git clone https://github.com/domenicolorenti/itinera.git
```  


### Frontend

##### Install dipendencies
```bash
yarn install
```

#### Run React development server 
```bash
yarn start
```

### Backend

#### Export JAR
```bash
mvn clean install
mvn clean package
```

#### Build & Run container
```bash
docker build -t <container-name> .
docker run -dp <local-port>:<container-port>
```

#### Use on K8s local cluster

```bash
minikube start
helm install <package-name>
```
The helm package use container image in docker.io/domenicolorenti
#### View pods list
```bash
kubectl get pods 
```


Before running the project, make sure you have Docker, Kubernetes and Helm installed on your system. Instructions for setting up the project are provided separately in each microservice folder.

  

Remember to execute the Helm commands to bundle the Ranking and Review services together into a single PBC. The commands can be found in the Helm documentation provided in the respective folders.

  

## Contact

  

For any further queries, please reach out to me [domenicolorenti.dev@gmail.com](mailto:domenicolorenti.dev@gmail.com) or open an issue in the repository.

  

## Acknowledgments

  

I would like to express my heartfelt gratitude to [NTT Data](https://www.linkedin.com/company/nttdata/) for their unwavering support throughout this project. Their contribution and guidance have been invaluable in its success.

I am especially grateful to [Marco Marano](https://www.linkedin.com/in/marco-marano-31a02832/) for handing me the opportunity to work in a professional and highly skilled work environment.

Furthermore, I want to extend my sincerest thanks to my corporate mentor, [Davide Lienhard](https://www.linkedin.com/in/davide-lienhard-8b3922187/). I owe all the acquired skills and knowledge to his continuous guidance and support. His mentorship has been instrumental in my personal and professional growth.

Thank you all for your contributions and support.
