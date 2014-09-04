BigData_for_Energy_Efficiency
=============================
### !!!Under Construction!!!####

This project is an endeavour to provide a proof of concept for using Big Data along with advanced analytics techniques to solve issues for improving energy efficiency. In this project we used some sample data sets provided by "Technical Research Centre of Finland - VTT". These data sets were collected using specialized metering devices installed by VTT in a group of buildings. For sake of of anonymity the names and locations of the buildings are replaced by hypothetical labels. Following is a list of energy effeciency use cases that were considered as part of this proof of concept.

1. Calculating the base load of the building to identify non user consumption of buildings.
2. Classifying the buildings on the basis of the energy efficiency and analyse the seasonal shifts in this classification.
3. Predicting daily energy consumption of various household devices on the basis of previous consumption pattern.
4. Collecting Twitter data for energy related topics using keyword filtering. 

Following is the list of tools used for Big Data, advanced analytics and results visualization.

* Apache Hadoop
* Apache Pig 
* Apache Flume
* Apache Hive
* Apache oozie
* Cloudera Impala
* MongoDB (Optional)
* R Programming for Statistical Computing
* Weka 
* Tableau Public 

We used Cloudera CDH4 for Apache Hadoop, Pig, Hive, Flume, Ozzie and Cloudera Imapala.

## Software Architecture

![alt tag](https://github.com/hazznain/BigData_for_Energy_Efficiency/blob/master/images/iplatform.png)

##Implementation
###Cloudera CDH4
For this proof of concept or any demo use Cloudera CDH4 quick virtual machine can be used that is available via [Cloudera official website for Quick VM ](http://www.cloudera.com/content/support/en/downloads/quickstart_vms/cdh-4-7-x.html).

For using the concept presented in this proof concept in a production environment, We recommend that you install Cloudera CDH 4.0 in pseudo distributed single node or multi node modes. We found this very helpful step by step instruction of installing CDH4 published by AVINASH KUMAR SINGH [Step by step guide for installing and configuring CDH4](https://docs.google.com/file/d/0Bx6N95pJhrROblJiaEJ0dHpwVmc/edit). Detailed cloudera documentation are official via their official documentation pages,[Ways to install CDH4](http://www.cloudera.com/content/cloudera-content/cloudera-docs/CDH4/4.2.0/CDH4-Installation-Guide/cdh4ig_topic_4_2.html).

### Using Apache Pig and R scripts to classify buildings on basis of energy effeciency

Following steps can be used to analyze the data for given use cases. These steps can be used with CDH4 in any configuration. We have tested it using Cloudera CDH4 quick VM. 

1. Download material in this reposiroty using following command. (Git installation is a pre-requisite)

`git clone https://github.com/hazznain/BigData_for_Energy_Efficiency`

2. Extract and copy the data to HDFS

`cd BigData_for_Energy_Efficiency/`

`unzip data.zip`

`hadoop fs -copyFromLocal hld_masked.csv .`
The above command will copy the data file with hourly consumption data to HDFS in user's home hdfs directory.

To view if the file is copied correctly, use following command
`hadoop fs -ls`

3. Using the Apache Pig script to pre-process data



`hadoop fs -ls`
 
`pig -f energy_consumption_matrix.pig`

`hadoop fs -copyToLocal energy_consumption_matrix ` .

`cd energy_consumption_matrix`

`more part-r-00000`

