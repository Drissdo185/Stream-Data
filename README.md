# First Click Attribution for E-commerce

## Description
This repository provides tools for implementing First Click Attribution in e-commerce. It helps track the initial user interactions, such as clicking on ads or promotional links, that lead to product purchases. Analyzing these first clicks enables businesses to optimize marketing strategies for better ROI.

Our objectives are:

1. Enrich checkout data with the user name. The user data is in a transactional database.
2. Identify which click leads to a checkout (aka attribution). For every product checkout, we consider the earliest click a user made on that product in the previous hour to be the click that led to a checkout.
3. Log the checkouts and their corresponding attributed clicks (if any) into a table.


![image alt text](<assets/images/overrall.png>)

## Concepts
![image alt text](<assets/images/concept.png>)

## Run Project 

### Install Libraries
```bash
pip install -r requirements.txt
```

Then run the following command to start the project:

```bash
docker compose up -d 
```
![image alt text](<assets/images/runproject.png>)

After run that command, you have to wait a few minutes to start the project.

When you see that, it means that the project is running:
![image alt text](<assets/images/finish.png>)

## Access Flink UI and Grafana monitoring

### Flink UI

Fistly, you need run this command to fake stream data
```bash
docker exec jobmanager ./bin/flink run --python ./code/checkout_attribution.py
```
And then you can access the Flink UI with the following URL:
```bash
http://localhost:8081/
```
The result of the job will be displayed in the Flink UI.

![image alt text](<assets/images/flink.png>)

### Grafana
To access the Grafana monitoring, you need to open your browser and access the following URL:
```bash
http://localhost:3000/
```
![image alt text](<assets/images/grafana.png>)
