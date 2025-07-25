# How to Contribute

We'd love to accept your jobs, reports, exports, and any contributions to this project. There are just a few small guidelines you need to follow.

## Contributor License Agreement

Contributions to this project must be accompanied by a signed [Contributor Agreement](ContributorAgreement.txt).
You (or your employer) retain the copyright to your contribution, this simply gives us permission to use and redistribute your contributions as part of the project.

## Checklist before contributing

When adding your contribution using a Pull Request, you will be asked the following questions:

1. Confirm that you have the right to submit the jobs, reports, exports, etc. that is being contributed. Please consider the origin of your code and confirm you have the appropriate rights to make the submission subject to the Apache 2.0 license that applies to everything in this repository of data quality and data governance jobs, reports, exports, and any other contributions. If so, follow the instructions for the [Contributor Agreement](ContributorAgreement.txt) (which is based on the industry-standard Developer Certificate of Origin (DCO))
2. Confirm that your contribution does not include any personally identifiable information (PII), for example, in any examples used in your README file.  We would like all data to be anonymized before submitted to this project.
3. Confirm your contribution does not include any encryption or other export-controlled technology.  

## Guidelines for contributions

1. Make sure your contribution is provided in the following formats:
    - DataFlux jobs are submitted either as a Package file (.dpf) or as a Data Definition File (.ddf).  
      - We would also like a sampling of data submitted with the job.
      - We would like a clear explanation of what the job is doing.
      - If this job was used with a presentation, whenever possible please include the presentation.

    - SAS Studio flow jobs are submitted as a flow (.flw)
      - We would also like a sampling of data submitted with the job if the data is not shipped with Viya OOTB.
      - We would like a clear explanation of what the job is doing.
      - If this job was used with a presentation, whenever possible please include the presentation.

    - SAS Visual Analytics reports as submitted as an exported file with all dependencies included (.json).
      - We would also like a sampling of data submitted with the exported file if the data is not shipped with Viya OOTB.
      - We would like a clear explanation of what the job is doing.

    - SAS Business Data Network files should be submitted as an export (.xml)
      - We would like a clear explanation of what is in the exported BDN export.

2. Store your contribution in its own subfolder and follow the same structure as in the **_template** folder
3. All submissions, including submissions by project members, require review. We use GitHub pull requests for this purpose.
     Consult [GitHub Help](https://help.github.com/articles/about-pull-requests/) for more information on using pull requests in general.
     The next section will go through the detailed steps from start to finish.  

## Steps to perform when contributing to the Data Governance & Data Quality Archive

High-level the procedure is as follows: Create a **Fork** of the public repository under your own GitHub account, create a dedicated folder in the forked repository to contain your contribution including documentation, then issue a **Pull request** which makes your contribution available for review by the maintainers of the public repository, and answer the questions being asked. When accepted, the maintainer will merge into the public repository. 

There are multiple tools that can be used to do all of this. A list of tasks to perform using a combination of GitHub webUI and [GitHub Desktop](https://desktop.github.com/) is shown below: 

|Task | Link to recording (animated gif, no sound) |
| --- | --- |
| 1. (GitHub webUI) [Login to GitHub](https://github.com/) using your own account (a personal GitHub account should work just fine) |  no recording |
| 2. (GitHub webUI) Issue a **Fork** request on the [public SAS DQ and DG Assets repository](https://github.com/sassoftware/sas-dqdg-assets) | [Link to recording](docs/contributing/1.%20Fork%20repository%20-%20GitHub%20webUI.gif) |
| 3. (GitHub Desktop) **Clone** your **Fork** to a local repository (on your local harddisk) | [Link to recording](docs/contributing/2.%20Clone%20forked%20repo%20to%20local%20disk%20-%20GitHub%20Desktop%20app.gif) |
| 4. (Local directory) Create a dedicated folder for your contribution by simply copying the **_template** folder and name it appropriately, and upload your files | [Link to recording](docs/contributing/3.%20Add%20custom%20step%20to%20local%20directory%20and%20push%20to%20forked%20repo%20-%20GitHub%20Desktop%20app.gif) |
| 5. (Local directory) Update the **README.md** file in that dedicated folder to reflect your asset and replace the screenshots in the **img** subdirectory with screenshots of the UI of your assets | See recording for #4 |
| 6. (GitHub Desktop) Commit the changed files and push them back to your **Forked** repository (aka. origin remote repository) | See recording for #4 |
| 7. (GitHub webUI) **Sync** your **Forked** repository **before** issuing a pull request ) | [Link to recording](docs/contributing/3c.%20Sync%20fork%20before%20issuing%20pull%20request.gif) |
| 8. (GitHub Desktop/GitHub webUI) From the **Forked repository**, initiate a **Pull request** to make your contribution available for review by the maintainers of the parent repository | [Link to recording](docs/contributing/4.%20Create%20pull%20request%20and%20attach%20DCO%20-%20GitHub%20webUI.gif) |
| 9. (GitHub webUI) As part of the **Pull request** you will be shown a message in the GitHub webUI that asks you to answer the questions outlined in "Checklist before contributing" shown above, and also **attach a signed version** of the [Contributor Agreement](ContributorAgreement.txt). <br/>**Note**: Attach your signed agreement to the pull request message in the webUI as shown in the recording, do not put it in your forked repo. | See recording for #8 |
| 10. (GitHub webUI) Respond to questions/requests from maintainers | [How to view your pull request?](docs/contributing/5.%20How%20to%20view%20your%20pull%20request%20-%20GitHub%20webUI.gif) |   

Note for task #8: This can be done directly from the **GitHub webUI** or initiated from the **GitHub Desktop application**. The latter will open a browser tab showing the Pull request page in the GitHub webUI.

After you have submitted the pull request the following will happen:
  * GitHub will notify the **maintainers** of the parent repository of a contribution/update
  * The **maintainers** will review the request, ask additional questions if needed, and then if everything is okay
    perform a **merge request** 
  * Once the **merge request** has finished successfully, your contribution is available in the public repository and you (the contributor) 
    will automatically be notified by GitHub 
