# cassandra docker세팅 절차

## Run Dokcer Container:
```docker
docker pull cassandra

docker run -p 7000:7000 -p 7001:7001 -p 7199:7199 -p 9042:9042 -p 9160:9160 --name cassandra -d cassandra:latest

docker exec -it {container_id} bash

cqlsh
```

## Cassandra Commands:

```cql
DESCRIBE CLUSTER
DESCRIBE KEYSPACES
SHOW VERSION

CREATE KEYSPACE my_keyspace WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
USE my_keyspace;
CREATE TABLE user (first_name text, last_name text, title text, PRIMARY KEY (last_name, first_name));
DESCRIBE TABLE user;
INSERT INTO user (first_name, last_name, title) VALUES ( 'Bill', 'Nguyen', 'Mr.');
SELECT * FROM user WHERE first_name='Bill' AND last_name='Nguyen';

SELECT * FROM user where last_name = 'Nguyen';
SELECT * FROM user where first_name = 'Bill'; 
# InvalidRequest

SELECT COUNT (*) FROM user; 
# Warnings : Aggregation query used without partition key

# delete a column
DELETE title FROM USER WHERE
          first_name='Bill' AND last_name='Nguyen';


SELECT * FROM user WHERE first_name='Bill'
      AND last_name='Nguyen';
     last_name | first_name | title
    -----------+------------+-------
        Nguyen |       Bill |  null

(1 rows)


# delete the entire row
DELETE FROM USER WHERE first_name='Bill'
      AND last_name='Nguyen';


SELECT * FROM user WHERE first_name='Bill'
      AND last_name='Nguyen';
     last_name | first_name | title
    -----------+------------+-------
(0 rows) 

TRUNCATE user;
DROP TABLE user;
```