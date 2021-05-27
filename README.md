# Covid19-data-pipeline-with-Airflow-MySQL-on-Docker

## Set up
#### 1. Install Docker
https://docs.docker.com/get-docker/

#### 2. Run docker-compose 
 - Set directory
```sh
CD 'D:\My File\Documents\Code\Covid19' # your path
```
 - Run docker-compose
```sh
docker-compose up -d
```

#### 3. Set up MySQL
 - Enter MySQL CONTAINER ID 
```sh
docker ps # copy MySQL's CONTAINER ID 
```
```sh
docker exec -it your_MySQL_CONTAINER_ID bash 
```
Example
![Example](https://i.imgur.com/m6FuuAF.png)
 - Enter MySQL
```sh
mysql -u root -p 
```
 - Create database
```sh
USE airflow_db
CREATE TABLE daily_covid19_reports (
  id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
  confirmed INT(6),
  recovered INT(6),
  hospitalized INT(6),
  deaths INT(6),
  new_confirmed INT(6),
  new_recovered INT(6),
  new_hospitalized INT(6),
  new_deaths INT(6),
  update_date DATETIME,
  source VARCHAR(100),
  dev_by VARCHAR(100),
  server_by VARCHAR(100)
);
```

#### 4. Set up Airflow (127.0.0.1:8080)
-  Create Connection
![Example](https://i.imgur.com/RBVZWwR.png)

## Get start
#### 1. Turn on covid19_data_pipeline DAG
#### 2. Check MailHog (127.0.0.1:8025)
#### 3. Query COVID-19 Report Data
```sh
SELECT * FROM daily_covid19_reports;
```

