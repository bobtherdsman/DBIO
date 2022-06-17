1-Extract DBIO.zip on c:\drive 
2-	The Dir creation 
      c:\SqlAssessmenTool 
         c:\SqlAssessmenTool\IN
         C:\\SqlAssessmenTool\Out
 
3-	 Create servers.txt for all Sql Server that need to be captured, and place it in SqlAssessmentTool\in
You can use IP address or SQL Server instance name and if port is different than the default port add  the port as well.
  
4-	To execute  open a cmd prompt navigate to c:\SqlAssessmentTool  and enter 
 c:\sqlAssessment\DBIO.exe login password collectiontime, Collection time is in minutes. Login needs to have Sysadmin permission. At this point we only support Sql server authentication 
5-	The tool will create the following tables in MSDB
  •	sql_collectionStatus  
  •	Sql_DbIO
  •	Sql DBIoTotal
The tool will create a Sql agent job for data collection the job will run every one minute and populate the tables in step 4
6-	The tool will generate 4 files in CSV format per server:
•	DB IO 
•	DB Mem usage 
           The file will be created on c:\sqlassessmentTool\Out
7-	You can re-run command in step 3 anytime if collection still running the tool will tell you how many minutes is left otherwise it will generate the output files.
8-	 to cleanup tables and Sql agent Job dbio login password 0 C , make sure  you run the tool first without the ‘C’ to get a dump of all files.

For bugs or comments reach out to bobtherdsman@gmail.com
