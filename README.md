# Homework3_zoomcamp


## Week 3 Homework


## Question 1:
Question 1: What is count of records for the 2022 Green Taxi Data??
- 65,623,481
- 840,402
- 1,936,423
- 253,647


from the picture we can see the answer is

- 840,402

<img src="https://github.com/juandavidlozano/Homework3_zoomcamp/blob/main/homework3.1.jpg" alt="Answer 1" width="1000" height="900">

the code

```SELECT COUNT(*) as total_records```
```FROM `test-402517.nytaxi.hw3_green_external_2022`;```


## Question 2:
Write a query to count the distinct number of PULocationIDs for the entire dataset on both the tables.</br> 
What is the estimated amount of data that will be read when this query is executed on the External Table and the Table?

- 0 MB for the External Table and 6.41MB for the Materialized Table
- 18.82 MB for the External Table and 47.60 MB for the Materialized Table
- 0 MB for the External Table and 0MB for the Materialized Table
- 2.14 MB for the External Table and 0MB for the Materialized Table


from the pictures we can see the answer is

- 0 MB for the External Table and 6.41MB for the Materialized Table

<img src="https://github.com/juandavidlozano/Homework3_zoomcamp/blob/main/homework3.2.1.jpg" alt="Answer 1" width="1000" height="900">
<img src="https://github.com/juandavidlozano/Homework3_zoomcamp/blob/main/homework3.2.2.jpg" alt="Answer 1" width="1000" height="900">

the code

```SELECT COUNT(DISTINCT PULocationID) AS distinct_pulocationids```
```FROM `test-402517.nytaxi.hw3_green_external_2022`;```

```SELECT COUNT(DISTINCT PULocationID) AS distinct_pulocationids```
```FROM `test-402517.nytaxi.hw3_green_BQ_2022`;```




## Question 3:
How many records have a fare_amount of 0?
- 12,488
- 128,219
- 112
- 1,622

from the pictures we can see the answer is

- 1,622

<img src="https://github.com/juandavidlozano/Homework3_zoomcamp/blob/main/homework3.3.jpg" alt="Answer 1" width="1000" height="900">

the code

```SELECT COUNT(*) AS zero_fare_amount_records```
```FROM `test-402517.nytaxi.hw3_green_external_2022```
```WHERE fare_amount = 0;```


## Question 4:
What is the best strategy to make an optimized table in Big Query if your query will always order the results by PUlocationID and filter based on lpep_pickup_datetime? (Create a new table with this strategy)
- Cluster on lpep_pickup_datetime Partition by PUlocationID
- Partition by lpep_pickup_datetime  Cluster on PUlocationID
- Partition by lpep_pickup_datetime and Partition by PUlocationID
- Cluster on by lpep_pickup_datetime and Cluster on PUlocationID

## Question 5:
Write a query to retrieve the distinct PULocationID between lpep_pickup_datetime
06/01/2022 and 06/30/2022 (inclusive)</br>

Use the materialized table you created earlier in your from clause and note the estimated bytes. Now change the table in the from clause to the partitioned table you created for question 4 and note the estimated bytes processed. What are these values? </br>

Choose the answer which most closely matches.</br> 

- 22.82 MB for non-partitioned table and 647.87 MB for the partitioned table
- 12.82 MB for non-partitioned table and 1.12 MB for the partitioned table
- 5.63 MB for non-partitioned table and 0 MB for the partitioned table
- 10.31 MB for non-partitioned table and 10.31 MB for the partitioned table


## Question 6: 
Where is the data stored in the External Table you created?

- Big Query
- GCP Bucket
- Big Table
- Container Registry


## Question 7:
It is best practice in Big Query to always cluster your data:
- True
- False


## (Bonus: Not worth points) Question 8:
No Points: Write a `SELECT count(*)` query FROM the materialized table you created. How many bytes does it estimate will be read? Why?
