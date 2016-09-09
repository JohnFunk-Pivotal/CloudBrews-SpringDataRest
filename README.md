# CloudBrews-SpringDataRest

spring data rest exercise
visit start.spring.io in a browser and check out what web, spa, data rest

curl start.spring.io/starter.zip -o demo.zip -d dependencies=web,jpa,data-rest,h2
unzip demo.zip

Add a few includes, and a annotated method to the Application definition in DemoApplication.java
curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/master/DemoApplication.java -o src/main/java/com/example/DemoApplication.java

Copy in Car.java and CarRepository.java
curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/master/CarRepository.java -o src/main/java/com/example/CarRepository.java

curl https://raw.githubusercontent.com/JohnFunk-Pivotal/CloudBrews-SpringDataRest/master/Car.java -o src/main/java/com/example/Car.java


mvn install
java - jar target/demo….jar

Open localhost:8080 in the browser
Explore the links in the rest response
do a search with:
http://localhost:8080/cars/search/find?make=ford

optionally push it to pcf
cf push datarest -p target/demo-0.0.1-SNAPSHOT.jar --random-route
