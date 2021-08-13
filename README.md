# CCDI-Portal-ETL
## Pre-requisites
Python 3.6 or newer

An initialized and running Neo4j database

## Add Dependencies
Run ```pip3 install -r requirements.txt``` to install dependencies. Or run ```pip install -r requirements.txt``` if you are using virtualenv. The dependencies included in requirements.txt are listed below:

pyyaml

neo4j - version 1.7.6

boto3

requests

## Configuration File
All the inputs of Data Loader can be set in a YAML format configuration file by using the fields defined below. Using a configuration file can make your Data Loader command significantly shorter.

An example configuration file can be found in config/config.yml

neo4j:uri: Address of the target Neo4j endpoint

neo4j:user: Username to be used for the Neo4j database

neo4j:password: Password to be used for the Neo4j database

schema: The file path(s) of the YAML formatted schema file(s)

prop_file: The file containing the properties for the specified schema

dataset: The directory containing the data to be loaded, a temporary directory if loading from an S3 bucket

## Load Data into Neo4j
Run following command to load data into neo4j database:
```python loader.py config/config.yml -p <neo4j password> -s model-desc/ccdi_portal_model_file.yaml -s model-desc/ccdi_portal_model_properties.yaml --prop-file model-desc/props-ccdi-portal.yml --no-backup --dataset data``` 

