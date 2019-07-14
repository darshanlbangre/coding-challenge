# Service Health Monitor

# Introduction

Setup a Java Spring project with a dependency on another service (could be a database, a JMS queue,
another public API, etc...). From there, create an endpoint where users can sign up for alerts about
service outages. That signup will require a name and email address. Your project should monitor its
dependencies and if it detects that the dependent service is unavailable, it should send an alert to all
users who have signed up.

# Project Overview
This project contains two applications i.e.. HealthMonitorService and RemoteService. The former keeps track of the service health status of the latter. The HealthMonitorService contains an in-memory database and exposes APIs for interested users to subscribe for an email notification of the heath status of RemoteService.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to install the software and how to install them
1. JDK 11
2. Maven
3. IDE (probably intelliJ)

## Installing

1. Checkout the project from master branch.
2. Run mvn clean package on both the projects individually.
3. Navigate to RemoteService/taget and start the remove service by executing "java -jar RemoteService-0.0.1-SNAPSHOT.jar" 
4. Navigate to HealthMonitorService/target and start the service by execting "java -jar health-monitor-service-0.0.1-SNAPSHOT.jar"
5. After the services have successully started, add the subscribers via POST REST API described below.

## REST APIs

* Add a subscriber
  * POST http://localhost:8080/api/service/status/subscribe
* Get all the subscribers
  * GET http://localhost:8080/api/service/status/subscribers


## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [SpringBoot](https://spring.io/projects/spring-boot) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc

