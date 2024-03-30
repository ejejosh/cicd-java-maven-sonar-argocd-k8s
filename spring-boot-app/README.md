# Spring Boot application

Checkout the repo and move to the directory

```
git clone https://github.com/ejejosh/cicd-java-maven-sonar-argocd-k8s.git
cd java-maven-sonar-argocd-helm-k8s/sprint-boot-app
```

Execute the Maven targets to generate the artifacts

```
mvn clean package
```

The above maven target stroes the artifacts to the `target` directory. You can either execute the artifact run as a Docker container.


```
java -jar target/spring-boot-web.jar
```

Build the Docker Image

```
docker build -t cicd-app:v1 .
```

```
docker run -d -p 8010:8080 -t cicd-app:v1
```

Access the application on `http://<ip-address>:8010`


## Next Steps

### Configure a Sonar Server locally

```
apt install unzip
adduser sonarqube
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip
unzip *
chmod -R 755 /home/sonarqube/sonarqube-9.4.0.54424
chown -R sonarqube:sonarqube /home/sonarqube/sonarqube-9.4.0.54424
cd sonarqube-9.4.0.54424/bin/linux-x86-64/
./sonar.sh start
```

Access the `SonarQube Server` on `http://<ip-address>:9000` 

