
# Quick start

## Build
```
mvn clean install
```

## Start Mongodb 

This demo application use MongoDB. We run MongoDB in Docker container.

```
docker run --name mongodb -p 27017:27017 -d mongodb/mongodb-community-server:latest
```

## Download the arex agent

```
curl -L -o arex-agent.jar https://d3fn6y7izhq8xo.cloudfront.net/arex-agent.jar
```

## Create an app on Softprobe console

Copy the following settings from the app settings
```
-Darex.service.name=a2aa3b1a3cd8c614 -Darex.api.token=QZMO:H1hUA7BIMvyGXf1GkuoIOjX+enFHt8EJgzvViay9gCdaH4JDhBNBPMfQ3yfdPiyjypTloF4o9OTFlhTVRlLXmw==  -Darex.storage.service.host=storage.softprobe.ai
```


## Run the application

```
java -javaagent:arex-agent.jar -Darex.service.name=a2aa3b1a3cd8c614 -Darex.api.token=QZMO:H1hUA7BIMvyGXf1GkuoIOjX+enFHt8EJgzvViay9gCdaH4JDhBNBPMfQ3yfdPiyjypTloF4o9OTFlhTVRlLXmw==  -Darex.storage.service.host=storage.softprobe.ai -jar target\mdb-spring-boot-0.0.1-SNAPSHOT.jar
```

Then query the API

```
curl http://localhost:8080/api/groceries
```

Now you should be able to see the recording


## Create test case from recordings

Click debug and send

Try to delete the records and rerun the test case. The result your test response should still be the same as we mocked MongoDB.