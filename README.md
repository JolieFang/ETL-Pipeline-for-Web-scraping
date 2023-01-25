# ETL-Pipeline-for-Web-scraping

The goal of this project is to develop a process that automatically extracts three different data sources - ATP tours, Twitter data and Bet365 data into two different databases - Mongodb and Postgres. Then load it to the containers that was created using Docker. This recorded all the processes within one file under Git, and the ETL pipeline was expected to run once the codes were initiated. The automated process will help stakeholders in efficiently replicating the ETL process, resulting in a reliable and ready-to-scale data processing pipeline.

## ETL Pipeline
![alt text](https://github.com/JolieFang/ETL-Pipeline-for-Web-scraping/blob/d10645d0c485c9b17fe57d4260087a88242e854e/ETL%20Pipeline.png)


## Tools used:
- Docker containers
- Apache Spark
- PostgreSQL database
- MongoDB database
- Python programming language
- Selenium
- ChromeDriver and Google Chrome

## Usage:

1. How to use Makefile and Dockerfile, run the below command to run all the necessary docker containers using terminal:
```
make all
```

2. To webscrape all listed websites, run:
```
make spark-submit
```
3. To reset (delete all table contents) the PostgreSQL database, run:
```
sh reset_postgres_database.sh
```
4. To copy the output files from docker container to your machine, run:
```
sudo docker cp -a spark:/opt/bitnami/spark/output_files/ ["target path in your machine"]

example:

sudo docker cp -a spark:/opt/bitnami/spark/output_files/ ~/Desktop/webscraping_files/
```
## Files:
Location of main python file:
```
pyspark/src/main.py
```
Location of output files (CSV, JSON, Parquet) - inside the 'spark' docker container:
```
spark:/opt/bitnami/spark/output_files/
```
