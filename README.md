# SSAS Query Log Decoder & Analyzer  

## Project Description  
The Crisp description for the project will be "CUBE FOR CUBE". This is an end-to-end BI solution for analyzing the Query log created by SSAS Server. The Query Log data is loaded into a dimensional model and a cube is built on top of it for analysis of cube usage.

This project has two components 

### SSASQueryLogDecoder  

This is a SSIS project which will decode the Dataset field in the Query log and load it into a Dimension model with the following dimensions

1.Dimension  
2.Date  
3.Time  
4.MeasureGroup  
5.User  

The variable to be set in the above project are

CubeUsageDB	- Database Name in which the tables will be created and data will be loaded  
CubeUsageServer	- Server for the above database  
OLAPDB	- Cube Name for which Querylog to be analyzed   
OLAPServer	- Cube server for which Querylog to be analyzed  
QueryLogDB	- Database in which Query Log is available  
QueryLogServer	- Server in which Query Log database is available  


### SSASQueryLogAnalyzer

This is SSAS project which is built on the Dimension model created and loaded by the above SSIS project. With this cube following types of reports can be generated

1. Highly used Measure groups
2. Unused Measure groups and Dimensions
3. Peak usage period in terms of year , Month , Day , Hour and Minute level
4. More adhoc reports with the published dimensions and fact.

Open the SSAS project , SSASQueryLogAnalyzer and Point to the Dimensional database created by the SSIS package.

#### Note : This project has been upgraded to work with Visual Studio 2015 and SQL Server 2016 
