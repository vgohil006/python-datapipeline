# A Python Data Pipeline Feed.
================================


- Imports Data from S3 Bucket, loads it into an Oracle Source Database
- Initiates AWS DMS Service for Data Migration to PostgreSQL Database
- Performs the Data transformations (create staging, info and mart schemas)
- Logs all steps of the process and triggers an email with loginfo once process is complete.



###### How to setup the pipeline on a server

On the data server, the data_prep_env virtual environment needs to be setup as follows:

1. Use SSH to connect to your server

2. Update the packages list  and install the pre-requisites
    + sudo apt update
    + sudo apt install software-properties-common

3. Add the deadsnakes PPS to the sources list
    + sudo add-apt-repository pps:deadsnakes/ppa
    + sudo apt-get update

4. Install Python 3.7
    + sudo apt install python3.7

5. Start a shell with root privileges
    + sudo -s -H

6. Install pip and update it to the latest version
    + apt-get install python3-pip
    + pip3 install --upgrade pip

7. Install virtualenv using pip3
    + /usr/local/bin/pip3 install virtualenv

8. Create a data_prep_env virtual environment directory
    + mkdir -p /opt/<dirname>/data-etl

9. Create a virtual environment using Python 3.7
    + cd opt/<dirname>/data-etl
    + virtualenv -p /usr/bin/python3.7 data_prep_env

10. Activate the virtual environment
     + source /opt/<dirname>/data-etl/data_prep_env/bin/activate

11. Install additional packages
     + apt-get install python3.7-dev

     + pip install beautifulsoup4
     + pip install psutil
     + pip install psycopg2-binary
     + pip install pyDes
     + pip install requests
     + pip install boto3
     + pip install cx_Oracle
     + pip install configparser
     + pip install botocore
     + pip install certifi
     + pip install docutils
     + pip install idna
     + pip install python-dateutil
     + pip install s3transfer
     + pip install setuptools
     + pip install six
     + pip install soupsieve
     + pip install urllib3
     + pip install wheel

12. Exit the virual environment
     + exit

13. Grant permissions on the data_prep_env to the main domain usergroup
     + chgrp -R <domaingroupusers> /opt/<dirname>/data-etl/data_prep_env
     + chmod -R g+w /opt/<dirname>/data-etl/data_prep_env

14. Install Java
     + sudo apt-get install openjdk-8-jdk

15. Run a pip list command to verify all the packages have been installed on the virtual env
     + cd /opt/<dirname>/data-etl/data_prep_env
     + pip list

  

