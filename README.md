# Station 2 - SpringDataRest

##Introduction
Spring Data REST is a very powerfull tool that exposes data sources such as databases as REST web services.  With very little code it analyzes your applicaitons domain model and exposes hypermidea-driven HTTP API that allows client services to traverse through your data.

In this exercise we'll build a very simple Spring Data REST application and deploy it to Pivotal Cloud Foundry.   Rather than hand writing a bunch of code, we'll start by using the Spring Boot Initializr to generate a template project with all the dependancies we need.

## Setup
Start by making a directory in your Google Compute Engine Console and changing into it
```
md springdatarest
cd springdatarest
```

## Investigate Spring Boot Initializr?
Spring Boot Initializr is a fast way to generate a skelton applicaiton and all the necessary dependancies for a spring boot appliciaton. Visit https://start.spring.io/ and switch into the full version to see the types of applicaitons it can create.

##Download the starter application template from start.spring.io
```
curl start.spring.io/starter.zip -o demo.zip -d dependencies=web,jpa,data-rest,h2 -d javaVersion=1.7
unzip demo.zip
```
## Look around at the code
The project code that Spring Boot Initializr just created for you.  It expanded out to the following directory structure.  Notice the starter template includes java code, static web templates, and even starter test harnesses for you.
![Tree View of the Application](https://github.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/blob/master/TreeViewOfApplication.png "Tree View of the Application")


##Modify DemoApplicaiton.java
Add a few includes and a annotated method to the Application definition in DemoApplication.java so it matches the code in the file above using vim, emax or nano in the Google Compute Engine Console add the highlited code in DemoApplication.java to the code in your environment.  

Or if you want to avoid typing you can copy the code into your environment with the following command:
```
curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/master/DemoApplication.java -o src/main/java/com/example/DemoApplication.java
```
##Copy in Car.java and CarRepository.java
You could type in the code from Car.java and CarRepository.java from this repo pretty quickly, but for this event, we're just going to copy it into your environment.
```
curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/master/CarRepository.java -o src/main/java/com/example/CarRepository.java

curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/master/Car.java -o src/main/java/com/example/Car.java
```

##Build and run the app
```
mvn install
java - jar target/demo….jar
```

## Open the app in the browser and explore some of the links in it  
Open http://localhost:8080 in the browser
  * Explore the links in the rest response
  * do a search with: http://localhost:8080/cars/search/find?make=ford

## Optional Step - Push the app to Pivotal Cloud Foundry
```
cf login -a api.run.pivotal.io -u demo2@johnfunk.com -o Channel -s Denver-CloudBrews
cf push datarest -p target/demo-0.0.1-SNAPSHOT.jar --random-route
```

If you are asked for a password please ask one of the helpers at the station to proide it.

## Login to Cloud Foundry
Open cloud foundry in a browser by visiting:  http://run.pivotal.io  
   *username: demo2@johnfunk.com  
   *password:  ask one of the helpers  

##Navigate to the Application in Pivotal Cloud Foundry
First click on the 'Denver-CloudBrews' space as shown below:
![CloudFoundrySpace](https://github.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/blob/master/CloudFoundrySpace.png "Space view on PCF")  

Next click on the link under the ROUTE lable as shown below:
![CloudFoundryApps](https://github.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/blob/master/CloudFoundryApps.png "Apps view on PCF") 

## Congradulations
Congratulations you just built a spring boot application on Google Compute Engine and pushed it to Pivotal Cloud Foundry.  Talk to the helper at the station to see what's next!

