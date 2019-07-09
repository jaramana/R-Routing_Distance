# Calculating Route Distance of Coordinates in a Table

This script calculates the distance between two coordinates in a row using routes from OSRM.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

What things you need to install the software and how to install them

```
library(osrm)
```

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
mydata <- read.csv("coordinates.csv", stringsAsFactors=FALSE)
```
route_distance <- data.frame(i = character(), j = character (),
                   time = numeric(), distance = numeric(),
                   stringsAsFactors = F)

```
k = 1
for (i in 1:5){
   for (j in i){
     route <- osrmRoute(src = mydata[i, c(7,10,9)],
                       dst = mydata[j, c(7,12,11)], sp = T)
     route_distance[k, ] <- as.vector(route@data[1,])
     k <- k + 1
     Sys.sleep(0.5)
   }
}
```

End with an example of getting some data out of the system or using it for a little demo

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

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

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

