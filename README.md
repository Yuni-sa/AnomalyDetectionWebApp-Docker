# Anomaly Detection Web App
This utility provides web interface (as well as RESTfull API) for anomaly detection functionality.

## How it works
The web interface (served with a node.js container) opens a connection to the c++ server container that holds the detection functionality and communicates with it to retrieve the needed information to the user.

## Project structure
The c++ server is in the folder *<u>cppDetectionServer</u>*, and the rest of the files are the web server.  The server is the file *<u>src/index.js</u>* . The html files served (using ejs) are in the folder *<u>views</u>*, adhearing to the MVC architecture.

## The Dockerized architecture
The project is split into two containers:  
    backend: The c++ server which the algorithms are on.  
    frontend: The node.js server which serves a web interface and handles requests.

## Prerequisites
To run the project all you need is docker installed and started on your machine.

## How to run
Open the terminal inside the project folder and type `docker-compose up -d`.

## Web interface
After the web server is run, it can be accessed via a web browser in the url
> localhost:8080

You simply pick an algorithm, upload a training and a detection csv files and click start.

## RESTfull API
The main entry point is (using the post method)
> localhost:8080

You need to supply a JSON object in the following format
`{
       alg: Regression algorithm/Hybrid algorithm,
       trainData: ...,
       detectData: ...
  }`
  Where trainData and detectData are the actual data (and not file names)
  The returned value is a JSON obejct that contains the anomalies.
  
## Screenshot
![image](https://user-images.githubusercontent.com/56509308/120115595-0a29e780-c18d-11eb-8b0c-d37a9f46c394.png)

