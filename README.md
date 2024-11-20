# Creating an application with a Spring Boot code sample

**Note:** The Spring Boot code sample uses the **8081** HTTP port.

Before you begin creating an application with this `devfile` code sample, Dockerize app with `Dockerfile` and Finally helm char to test in Openshift

First, test de demo, right click on file: `DemoApplication.java` and select option: `Run Java`

Appears something like: 

`
...TomcatWebServer  : Tomcat started on port(s): 8080 (http)
`

To test, navigate to: ```localhost:8080```

Stops the Run Test

To dockerize the demo, run this command:

```
docker build -f docker/Dockerfile -t juancvilla/springboot:4.0 .
docker image ls
```

To Publish you docker navigate to: `https://hub.docker.com/`

Go to repositories, and create a new repository: `juancvilla/springboot` with TAG: `4.0`

Go back to the command line and run this command:

```
docker push juancvilla/springboot:4.0
docker image ls
```

To test the docker run this command:

```docker run -p 8081:8081 juancvilla/springboot:4.0```

To test, navigate to: ```localhost:8081```

Stops the docker

To publish in Openshift, we will use helm chart. To create a helm structure:

```helm create springboot-demo```

Edit the file values.yaml:

```
Edit line 10:  repository: juancvilla/springboot
Edit line 14:  tag: "4.0"
Edit line 55:  type: NodePort
Edit line 57:  port: 8081
Edit lines 89-96:
#livenessProbe:
#  httpGet:
#    path: /
#    port: http
#readinessProbe:
#  httpGet:
#    path: /
#    port: http
```
