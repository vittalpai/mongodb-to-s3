# MongoDB To S3

This repository contains Kafka connector configuration files which enables real time data synchronization from MongoDB to AWS S3 Buckets.

## Prerequisites

- Kafka Cluster
- MongoDB Instance
- AWS S3 Buckets

## Setup 

- Download & Install the MongoDB Source & AWS Sink Connector Plugin in your Kafka Cluster 
    - https://www.confluent.io/hub/mongodb/kafka-connect-mongodb
    - https://www.confluent.io/hub/confluentinc/kafka-connect-s3

- Update the following in the `mongodb-source-connector.properties` connector configuration file.
    - `CONNECTION-STRING` - MongoDB Cluster Connection String
    - `DB-NAME` - Database Name
    - `COLLECTION-NAME` - Collection Name

- Update the following in the `s3-sink-connector.properties` connector configuration file.
    - `TOPIC-NAME` - Kafka Topic Name (i.e DB.COLLECTION name)
    - `S3-REGION` - AWS S3 Region Name
    - `S3-BUCKET-NAME` - AWS S3 Bucket Name where you wish to push the data.
    
- Deploy the connector configuration files in your Kafka Cluster. This will enable real time data synchronization from MongoDB to AWS S3 Buckets.

**Note**: The above connector push the data to the S3 bucket at a regular interval of time, these configuration can be modified based on the use case. Refer to the following documentation for more details. 
    - [MongoDB Souce Configuration](https://www.mongodb.com/docs/kafka-connector/current/source-connector/configuration-properties/)
    - [AWS S3 Sink Configuration](https://docs.confluent.io/kafka-connectors/s3-sink/current/configuration_options.html)