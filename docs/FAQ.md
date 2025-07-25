## How to easily transfer a Flow and a Custom Step to another SAS Viya environment?

If both the flow and the custom step it uses are stored in the same folder in SAS Content on the source environment, you can create
a so called **export package** that contains both items. This can be done using the **transfer-plugin to the SAS Viya CLI** or using 
the Export option available from the Content page in SAS Environment Manager.

In the target deployment you would use that same **CLI** or use **SAS Environment Manager** to import the package.

More details can be found in [Migration within SAS Viya: Tasks](https://documentation.sas.com/?cdcId=sasadmincdc&cdcVersion=default&docsetId=calpromotion&docsetTarget=n0ucexhkgs4rfgn12219vojr14nf.htm)

## What sample data is available for use in SAS Studio in a SAS Viya deployment?

1. The sashelp library - available in each SAS Studio session 
2. The sampsio library - a lesser known collection of SAS sample data that is available in every SAS Viya deployment
     - This library is not visible by default in the Libraries panel in SAS Studio. Here is how to make this library available in SAS Studio:
         * Open SAS Program using New -> SAS Program from the main menu
         * Run the following SAS code to get a listing of all the SAS datasets in the sampsio sample library that should be part of a default SAS deployment
           ```sas
           proc datasets library=sampsio; run;
           ```
         * This will display a list of tables in the Results window and will make the library sampsio available in the Libraries panel for your current SAS Studio session
         * TIP: Watch this [SAS Sample Data for Forecasting](https://www.youtube.com/watch?v=wX6mdBgYmXo&t=271s) recording on Youtube for more pointers to interesting sample data available from SAS
