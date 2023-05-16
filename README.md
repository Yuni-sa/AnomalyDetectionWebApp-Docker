# Anomaly Detection Web App
This utility provides a web interface and RESTful API for anomaly detection functionality.

## How It Works
The web interface, served with a Node.js container, establishes a connection to the C++ server container, which holds the detection functionality. It communicates with the server to retrieve the necessary information for the user.

## Project Structure
The C++ server is located in the *<u>cppDetectionServer</u>* folder.
The web server files can be found in the rest of the project.
The main server file is *<u>src/index.js</u>*.
The HTML files served (using EJS) are stored in the *<u>views</u>* folder, adhering to the MVC architecture.

## Dockerized Architecture
The project is divided into two containers:
Backend: The C++ server that contains the algorithms.
Frontend: The Node.js server that serves the web interface and handles requests.

## Prerequisites
To run the project, you need to have Docker installed and started on your machine.

## How to Run
Open the terminal inside the project folder and run the following command: `docker-compose up -d`.

## Web Interface
After starting the web server, you can access it through a web browser using the following URL:
> localhost:8080

In the web interface, you can select an algorithm, upload training and detection CSV files, and click "Start" to begin the anomaly detection process.

## RESTful API
The main entry point for the RESTful API is the following URL (using the POST method):
> localhost:8080

You need to supply a JSON object in the following format:
```json
{
  "alg": "Regression algorithm/Hybrid algorithm",
  "trainData": "...",
  "detectData": "..."
}
```
Make sure to replace trainData and detectData with the actual data (not file names). The API will return a JSON object that contains the anomalies.
## Screenshot
![image](https://user-images.githubusercontent.com/56509308/120115595-0a29e780-c18d-11eb-8b0c-d37a9f46c394.png)
