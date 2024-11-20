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

