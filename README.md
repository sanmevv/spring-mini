# Spring Boot application on K8s cluster (minikube)

1. From the terminal cd into your project directory and build project using ``` ./gradlew clean build ```
2. Start docker on system
3. Build docker image using : ```  docker build -t springboot-on-minikube .  ```
4. Run the docker container: ``` docker run -p 8080:8080 springboot-on-minikube ``` and verify calling url ``` localhost:8080/data ```
5. Now stop the container service 
6. start minikube using ``` minikube start --driver=docker ```
7. Enable docker env using command :  ``` eval $(minikube docker-env)  ``` 
8. Build docker image in minikube : ``` docker build -t springboot-on-minikube . ```
9. To see images : ``` minikube image ls ```
10. To enable ingress on minikube run following command :  ``` minikube addons enable ingress ```  
11. Verify ingress controller is running :  ``` kubectl get pods -n ingress-nginx ```
12. Next install and deploy helm chart on cluster : ``` helm install mychart ytkubechart ```
13. Verify ingress service using : ``` kubectl get ingress ```
14. Next add entry in ``` /etc/hosts ``` file
     - run ``` sudo vi /etc/hosts ```
     - enter password
     - press ``` i ``` key on keyboard
     - add entry : ``` 127.0.0.1  ytlecture.com ```
     - press ``` Esc ``` key on keyboard
     - press ``` :wq ```
15. verify changes using ``` cat /etc/hosts ```
16. Enable tunnel running command : ``` minikube tunnel ```
17. Then call url in browser : http://ytlecture.com/data
18. Successfully deployed 
19. Stop minikube using : ``` minikube stop ``` 

    
