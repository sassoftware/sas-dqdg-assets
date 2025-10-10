
# Data Quality and Entity Resolution with Loqate Verification of Phone, Email, and Address with Geocoding.

##  Objectives
   
This ia a SAS Studio Flow that demostrates how a typical DMStudio Data Job that does DQ/ER/Verification can be replicated as a No-Code SAS Studio Flow.

## Results and benefits

The result is that SAS/DataFlux customers can see how a move to Viya is possible.  
It should be noted that there still are no migration utilities for DataFlux jobs.  They still need to be recreated in Viya as SAS Studio Flows.


## Requirements

SAS Viya 2024.09+
The sample data and .json environment extract files containing the flow, and the Custom Steps used 

## Files overview

 - ACCOUNTS.CSV - 22 rows of fictional sample data. just import into the Public CASlib. and load into memory.
 - DQ_ER_2025_flow.json - import into your environment using SAS Environment Manager 
                        - if you need help with this see https://communities.sas.com/t5/SAS-Communities-Library/Migrating-SAS-Studio-Flows-containing-Custom-Steps/ta-p/945105
 - "Create CASlib and Session step.json" - import into your environment using SAS Environment Manager
 - "Custom Steps from Public GitHub.json" - import into your environment using SAS Environment Manager
 
 ## Use case process description

The demo SAS Studio Flow, called "Data Quality and Entity Resolution 2025.flw", has two swimlanes.  You can run them seperately, or all together.

For most demonstrations I just show the input data and point out the data quality problems and give the goal of cleaning up the data and eliminating duplicates.  Then I run the job, and show the resulting data at the end of the flow where the 22 rows have beeen reduced to 7 and the address info is cleaned and enhanced (e.g. missing Postal/Zip Codes provided, and ZipCodes enhanced to Zip+4 codes.  Then based on the time available, level of interest, and technical level of the audience I show how the data is transformed after each step.  I only go into each step and show how it is configured if the audience is technical and wants to see that.   

swimlane1 just creates the CAS session and assigns CASlibs, so that Public/ACCOUNTS table can be found.  
The Public/ACCOUNTS table needs to be loaded into memory if it hasn't been already. 

swimlane2 is the main flow and does multiple steps:

- Branch based on Country code, sending USA records down one stream, and CAN records down the other stream.  The USA steam uses ENUSA locale, and the CAN stream uses ENCAN locale.
- DQ Identify - identifies what type of data is found in the City, Prov, PostCode, and Phone columns.  Note uses a Custom Step, but could also be done with the Clean Data standard step.
- DQ RighFielding - moves errant data into the right places (e.g. moving emails to the Email column, and Phone Nubmers to the Phone Column)
- Calculate Columns - creates a CPP field by concatenating City, Prov, PostCode
- Parse Data - Parses the CPP
- Standardize Data - Standardizes City, Prov, Postal/ZIP, Phone
- Verify wtih Loqate - Verifies Phone, Email, Address, and gets Geocoding
- Manage Columns - selects the resluting columns of interest from Loqate, and reorders them to follow the input columns
- Union Rows - brings the CAN and USA streams back together
- Match Codes - creates Match Codes on Name, Address, City, Phone.  note, this uses ENCAN for both the CAN and USA data.  could be down seperately before the Union, but doesn't really make much difference.
- DQ Clustering - clusters the rows based on rules: Name+Address+PostCode or Name+Address+City+Prov or Name+Phone or Name+Email
- Manage Columns 3 - just moves the Cluster ID column so that it is the first column, not the last column
- DQ Surviving Record - selects the surviving record from the cluster using a simple row rule - just picks the row with the highest Address Verification Code (AVC) - more complex row rules and field rules can be implemented, some in this no-code step, but some might need to be done in a code node (e.g. summing up the Amount field for the cluster).
- Manage Columns 4 - just reorders the columns so that the Verified Address fields are among the first

I have left out a final step, which could be a Load Table step, since it depends on what you wanted to do with these results.  But this is an opportunity to show how you would just drag that step onto the end of the flow.


