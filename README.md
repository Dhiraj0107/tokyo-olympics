# Tokyo Olympics

This comprehensive end-to-end data engineering project revolves around the Tokyo Olympics dataset, showcasing a data pipeline executed on the AWS cloud. Beginning with loading data into Amazon S3 using boto3, the process includes Glue Crawler and Athena integration for automated table definitions and querying. Further stages involve data extraction to the local system for cleaning with Pandas, storage in Redshift for the creation of dimension and fact tables according to the below model using SQL, subsequent extraction back to S3, and loading data to the local system using AWS CLI. The project also encompasses the consolidation of data segregated into different files for each table into a single file on the Windows command prompt. The finale involves a dynamic Power BI dashboard, employing DAX functions for visualization.

##### Data Source: https://www.kaggle.com/datasets/piterfm/tokyo-2020-olympics

#### Data Model for Tokyo Olympics 2020

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/4843a13e-5da7-4681-97cb-84895ba9e02d)


#### Created S3 bucket and loaded the data from local to S3 using Python (AWS-Project.ipynb):

![image](https://github.com/Dhiraj0107/Airbnb-Amsterdam/assets/118677714/b5f115d9-6662-47e1-b27d-08a269e1e83c)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/e8738be0-001d-4ef7-85a6-c2c7bf7a2fe9)


#### Created Glue crawler and loaded tables to Athena for querying and analysis:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/2efd2c5a-ffb6-4c8d-a3e0-a0eca0d22b2e)


#### Next, performed ETL on the data using Python (AWS-Project.ipynb) and loaded the cleaned tables back to S3:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/1c107a77-1af1-47c3-9611-311740d9570b)


#### Connected to Redshift Serverless and created and loaded data to it using the below queries:


##### Athletes table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/4ab6a55b-c927-4247-930c-59e4c424e877)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/f92e204a-815b-4d6a-a1d6-0d0277ae6f49)


##### Coaches table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/6ad41d17-98e8-47a8-81ae-2f09e1b7b2aa)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/d88241c1-686a-4af4-9f8d-5f869fc446da)


##### Medals_Totals table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/938682b2-bd50-4ca0-bc35-da367f7c13ac)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/c141d87d-11ab-43d9-aa8b-cd9ff6541d57)


##### Medals table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/b02ad8dc-d035-498e-b6a2-bc73c5b91b53)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/6c67c58f-7a8b-43ff-b1cf-7e417b761a00)


##### Technical Officials table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/67afbcf6-d80b-43c9-b769-280dee4305c6)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/403024c2-e40c-40d8-8ba9-27bce05fac58)


#### Created fact and dimension tables as per the above data model:


##### factOlympics table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/98e4bd6f-4b03-4309-a8e8-99e18aba4eaf)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/70aec895-b818-42d3-b4dd-89bbc56d4854)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/93fa2a56-6531-4baa-8ef8-e7aeb9e4b7e8)

##### dimCountry table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/1e987a4b-a21a-4950-8ab2-52ce06c4898c)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/7bb8ad62-1004-487e-bc93-9424afd6af72)

##### dimAthletes table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/86abf820-607f-4a6f-8805-511642a16b9b)

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/cc016df3-962b-4271-b3a1-9b1129da2471)

##### dimCoaches, dimMedals_Totals, dimMedals, dimTechnical_Officials tables:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/86ee2d85-6d77-4ed4-a474-a1ced7bc53f2)


#### Loaded the data back to S3:

##### dimTechnical_Officials table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/c8e814f7-336b-4c75-b59c-8e6b53c42b6d)

##### dimMedals table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/f7192ec1-d636-457c-9620-9620f40b95d8)

##### dimMedals_Totals table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/e48abfdc-727a-4060-b578-0068d29e7b62)

##### dimCoaches table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/f3956e11-456a-4fac-ab1b-31d8aaffe1a7)

##### dimAthletes table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/ad6b4114-c249-4a6f-897b-93071e5cdce1)

##### dimCountry table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/56668114-7099-4882-8801-5ed1943c7f96)

##### factOlympics table:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/cc15720c-cee7-4053-8417-2a866a6ae882)


#### Copied the data from S3 to local using the below commands on AWS CLI for analysis and reporting:

aws s3 cp s3://redshift-retrieval-bucket/final-files/ "C:/Users/Dhiraj/Downloads/My Projects/AWS/Datasets_For_Analysis/Technical_Officials/" --recursive

aws s3 cp s3://redshift-retrieval-bucket/Medals/ "C:/Users/Dhiraj/Downloads/My Projects/AWS/Datasets_For_Analysis/Medals/" --recursive

aws s3 cp s3://redshift-retrieval-bucket/Medals_Totals/ "C:/Users/Dhiraj/Downloads/My Projects/AWS/Datasets_For_Analysis/Medals_Totals/" --recursive

aws s3 cp s3://redshift-retrieval-bucket/Coaches/ "C:/Users/Dhiraj/Downloads/My Projects/AWS/Datasets_For_Analysis/Coaches/" --recursive

aws s3 cp s3://redshift-retrieval-bucket/Athletes/ "C:/Users/Dhiraj/Downloads/My Projects/AWS/Datasets_For_Analysis/Athletes/" --recursive

aws s3 cp s3://redshift-retrieval-bucket/Country/ "C:/Users/Dhiraj/Downloads/My Projects/AWS/Datasets_For_Analysis/Country/" --recursive

aws s3 cp s3://redshift-retrieval-bucket/Olympics/ "C:/Users/Dhiraj/Downloads/My Projects/AWS/Datasets_For_Analysis/Olympics/" --recursive


#### Consolidated the data segregated into different files for each table into a single file using the below commands on Windows machine:

copy *.txt* "C:\Users\Dhiraj\Downloads\My Projects\AWS\Consolidated_Datasets_For_Analysis\Technical_Officials\Technical_Officials.csv"

copy *.txt* "C:\Users\Dhiraj\Downloads\My Projects\AWS\Consolidated_Datasets_For_Analysis\Medals\Medals.csv"

copy *.txt* "C:\Users\Dhiraj\Downloads\My Projects\AWS\Consolidated_Datasets_For_Analysis\Medals_Totals\Medals_Totals.csv"

copy *.txt* "C:\Users\Dhiraj\Downloads\My Projects\AWS\Consolidated_Datasets_For_Analysis\Coaches\Coaches.csv"

copy *.txt* "C:\Users\Dhiraj\Downloads\My Projects\AWS\Consolidated_Datasets_For_Analysis\Athletes\Athletes.csv"

copy *.txt* "C:\Users\Dhiraj\Downloads\My Projects\AWS\Consolidated_Datasets_For_Analysis\Country\Country.csv"

copy *.txt* "C:\Users\Dhiraj\Downloads\My Projects\AWS\Consolidated_Datasets_For_Analysis\Olympics\Olympics.csv"


#### Finally, developed a dashboard on Power BI for analysis:

![image](https://github.com/Dhiraj0107/tokyo-olympics/assets/118677714/0f1b6e6b-5a8f-45f9-b37d-1d62abf6e1c7)

#### DAX Functions used for developing the dashboard:

Number of Medals Won = count(Medals[country])

Count_Bronze = CALCULATE(COUNT(Medals[country]),Medals[medal_type]="Bronze Medal")

Count_Silver = CALCULATE(COUNT(Medals[country]),Medals[medal_type]="Silver Medal")

Count_Gold = CALCULATE(COUNT(Medals[country]),Medals[medal_type]="Gold Medal")

Birth_Year = IF(FORMAT(Athletes[birth_date],"dd-mm-yyyy") = "Not mentioned", BLANK(), YEAR(Athletes[birth_date]))





## Technologies used:

### AWS Services:

- Amazon S3
- AWS Glue
- Amazon Athena
- Amazon Redshift

### Python Libraries:

- boto3
- pandas

### Data Visualization:

- Power BI





## Acknowledgments and Lessons Learned

During the development of this project, I encountered challenges and made mistakes, one of which was not adding a foreign key column in the Country table. Unfortunately, due to exceeding S3 limits, I'm unable to make corrections without incurring additional costs.

### Lessons Learned:

- **Always Double-Check Changes:** Take the time to thoroughly review any changes before implementation to avoid oversights.
- **Cost Considerations:** Be mindful of AWS service limits and associated costs, especially when dealing with large datasets.

While this mistake has its limitations in correction, it serves as a valuable learning experience for future projects.

