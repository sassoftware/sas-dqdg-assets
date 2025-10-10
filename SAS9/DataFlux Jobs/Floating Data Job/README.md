## (DataFlux) QKB Floating Data (Right Fielding)

#### Description

------

The DQ Basic Functionality job is a great example job for people looking to see what DataFlux can do as far as data quality is concerned.  

The job starts with taking un-fielded data that cannot be easily cleaned or used for anything and running it through the "Right Fielding" node.  The "Right Fielding" node uses the QKB to allow users to look at the content of a row column by column  and field it into a common column schema across all of the records. This allows users to quickly and easily take data and turn it from unusable to usable without writing any code. 

![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Floating Data Job\img\QKB_Floating_Data_Job_input.jpg)

The second step of the job uses the "Right Fielding" node to map the fields to evaluate on input and then select potential output fields to write to after the Field Content definition has determined what each data token actually is.  As we said above all of this fielding work is taken care of automatically and no code needs to be written by the DataFlux user.

![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Floating Data Job\img\QKB_Floating_Data_Job_right_fielding.jpg)

Next we run the now fielded data through standardization so that we can automatically take care of spelling, punctuation, formatting, etc.  This step is using the QKB and all of the inherent definitions within the QKB to standardize how different tokens are displayed based on language and location.

![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Floating Data Job\img\QKB_Floating_Data_Job_fielded_and_standardized.jpg)

The last step of this job now has the fielded non standardized data next to its standardized data counterpart so that you can show how we now have data that is ready for use.  This data should still be enriched and run through a matching process if moving this to a downstream analytics or visualization project, but we have within a few short steps gone from completely un-fielded data to fielded and standardized data.
  ![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Floating Data Job\img\QKB_Floating_Data_Job_output.jpg)

 

![GITLAB Image](./img/Screenshot_1_2.jpg)




| Job Specifics    | Explaination |
| ---------------- | ------------ |
| Data Source      | messy.txt    |
| QKB Version      | CI33         |
| DataFlux Version | 2.10         |

#### Change Log

------

Version 1.0 (10/09/2025)

- Initial Version