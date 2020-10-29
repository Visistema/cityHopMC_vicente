cityhopMC_vicente

RESTful service using Spring Boot

cityhopMC_vicente determines whether two given cities are connected by known roads. It provides a single RESTful endpoint that answers the query, "Can I get from city A to city B?"

It loads the roads from a local text file--which means: a "known road" is a road found in the file.

Install and Run (macOS, Linux)

Prerequisite: Java 11

To install and launch the app, open a terminal and do the following:

cd to the dir in which you want to install the project (i.e., the project's parent dir).
clone the github project via
git clone https://github.com/masterCard/cityhop.git
cd to the project home dir
Launch the app via
./gradlew bootRun
This loads the default file city.txt
ALTERNATE: to read roadmap data from non-default location, do
./gradlew bootRun --args=myRoadMapData.txt
Be sure to replace "myRoadMapData.txt" with the path to the file you want to load.
Logs get written to standard output. Overrides to default log levels are set in src/main/resources/application.properties

JUnit tests may be run from the command line via ./gradlew test

Usage

Send HTTP GET requests to localhost port 8080, naming origin and destination cities:
-----------------------------------------------------------------------------------------------
http://localhost:8080/connected?origin=city1&destination=city2
If city1 is connected to city2 by any path along known roads, the response will be: yes.

If not, or if the request is not formatted properly, the response will be:
no.

------------------------------------------------------------------------------------------------
