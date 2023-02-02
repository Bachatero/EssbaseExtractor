# Essbase data extraction engine

Tired of using unstable SmartView for MS Excel and Essbase db extract is not an option? Have your data pulled to SQL database and do your data analysis there.

Doc under construction

## About

EssbaseToolsLauncher.py v2.1 is a parallel auto chunking data extraction tool. It utilizes Essbase.py module (https://github.com/jasonwjones/essbasepy) 
to extract data from Oracle Hyperion Essbase cube and populates relational table in SQL Server.

## Features

1. Spawns multiple background subprocesses to load chunks of data in parallel. 

2. Introduces global parallel limit and Account type limit parameters to take care of parallel processing resource management

3. The level of parallelism is configurable

4. Failed chunk is auto restartable (with adjustable number of retries) and the whole loading process can be restarted right from the point 
it failed at (i.e. only failed chunks and chunks not yet processed get (re)loaded)

5. Solution includes optional SSIS UI packages 


## Prerequisites

 1. MS SQL Server (developed and tested @2016, needs to be checked against other versions)

 2. Python (compatible with 3.5 and 3.6) available at the same location where MS SQL Server is installed
 
 3. Pypyodbc module
 
 4. Essbase.py MaxL module 
 
 5. Oracle Essbase client libs (for details, please, refer to https://github.com/jasonwjones/essbasepy )

 6. SSIS runtime service/Visual Studio with Integration services
 

## Installation

 The installation of the application consists of two parts: 

 1. SQL Database side
 
 2. Python engine


### Setting up SQL Database environment

 1. Create separate SQL database instance to house dimension/temporary staging/config tables and SQL code 
 
 2. Run database objects DDL definition scripts
 
 3. Fill dimension tables with data. Use provided script ... with sample data. Optionally use provided SSIS package and Excel template file.



### Setting up Python side of application 

 1. Clone the contents of EsstoolChunk to your local directory.
 
 2. Edit EsstoolChunk/MyModule/__init__.py file to reflect local PATH specifics ... 

 3. Have your Essbase server hostname, username and password ready. Use provided encr.py script to encrypt the password. Replace s and c python lists with generated strings in the __init__.py file, respectively. 

 4. Compile python binary (refer to Pyinstaller video @https://youtu.be/AT23SLTBRQo). You may optionally leave out this step.




## Usage


## Contact
 
  Send email to mrc.kantor@gmail.com for help and possible issues you encounter. Thank you.


## Credits
 

## Disclaimer

  Of course, there will be one


## Todo

  1. Consolidate istallation steps into a single bundle that would simplify the process
  2. Add data staging phase

 
