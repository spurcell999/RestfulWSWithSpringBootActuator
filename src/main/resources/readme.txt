server.port: 9000
management.server.port: 9001
management.server.address: 127.0.0.1
Run the server again:

$ ./gradlew clean build && java -jar build/libs/gs-actuator-service-0.1.0.jar

... service comes up on port 9000 ...
Test it:

$ curl localhost:8080/hello-world
curl: (52) Empty reply from server
$ curl localhost:9000/hello-world
{"id":1,"content":"Hello, Stranger!"}
$ curl localhost:9001/actuator/health
{"status":"UP"}