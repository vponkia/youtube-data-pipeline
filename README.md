# youtube-end-to-end-data-pipeline

### Introduction
This project aims to securely manage, streamline, and perform analysis on the structured and semi-structured YouTube videos data based on the video categories and the trending metrics.

### About Data
This kaggle dataset includes several months (and counting) of data on daily trending YouTube videos. Data is included for USA, Great Britain, Germany, Canada, and France, respectively regions, with up to 200 listed trending videos per day. [Youtube data](https://www.kaggle.com/datasets/datasnaek/youtube-new)

### Architecture
![Architecture Diagram](https://github.com/vponkia/youtube-data-pipeline/blob/main/you-tube%20data%20engineering%20.png)

### Services Used

1. **Amazon S3(Simple Storage Service)**: Amazon S3 is an object storage service that provides manufacturing scalability, data availability, security, and performance.
2. **AWS IAM**: This is nothing but identity and access management which enables us to manage access to AWS services and resources securely.
4. **AWS Glue**: A serverless data integration service that makes it easy to discover, prepare, and combine data for analytics, machine learning, and application development.
5. **AWS Lambda**: Lambda is a computing service that allows programmers to run code without creating or managing servers.
6. **AWS Athena**: Athena is an interactive query service for S3 in which there is no need to load data it stays in S3.

### Commands to transfer file from local to cloud(S3)

##### To copy all JSON Reference data to S3 location:
```
aws s3 cp . s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics_reference_data/ --recursive --exclude "*" --include "*.json"
```

#### # To copy all data files(CSV) to S3 location, following Hive-style patterns:

```
aws s3 cp CAvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=ca/
aws s3 cp DEvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=de/
aws s3 cp FRvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=fr/
aws s3 cp GBvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=gb/
aws s3 cp INvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=in/
aws s3 cp JPvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=jp/
aws s3 cp KRvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=kr/
aws s3 cp MXvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=mx/
aws s3 cp RUvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=ru/
aws s3 cp USvideos.csv s3://de-on-youtube-raw-ca-central-1/youtube/raw_statistics/region=us/
```
