## (DataFlux) Conditional Matching with Match Type Indicator

#### Description

------

The Conditional Matching with Match Type Indicator job show us how within a job users can create multiple match clustering rules.  The DataFlux matching process will not only allow users to have multiple clustering rules within a job, but users will be able to tell when a match is determined which of the matching criteria actually caused records to match.  

The job starts with the DataFlux Sample Contacts data set.  This data set gives us Company, Contact, Address, and Phone tokens which can if desired be used to determine matches.![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Matching\Conditional by Match Type\img\conditional_match_raw_data.jpg)

In the second step of this process, we have decided that we want to use Last (Family) name as one of the matching tokens.  We use the QKBs parsing function to extract the Family Name field from the Contact field.  If you look at the screenshot below, users have the ability to parse a name into a number of different tokens without writing a single line of code.
![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Matching\Conditional by Match Type\img\conditional_match_parse.jpg)

In the third step below, we are actually generating match codes for Address, City, Family Name, and Contact.  You can see that the sensitivity is set to 85 for all the tokens.  This Sensitivity of 85 (how close two strings within that token need to be to be considered a match) is the default.  The output of this step in an encoded representation of the token.  How that representation is created from the different tokens varies based on 20 years worth of experience on how to standardize a token.  Within the rules behind the scenes are nickname checking, phonetic reductions on terms, checking for "fat finger" misspellings, etc.
![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Matching\Conditional by Match Type\img\conditional_match_matchcodes.jpg)

In the fourth step, clustering, you can see in the screenshot below that three rules are defined to determine within this job if records match.  The clustering rules typically work from the most specific to the most generic, so in this situation Rule1 is Contact_matchcode and Address_matchcode and City_matchcode.  The second rule is Family Name_matchcode and Address_matchcode.  The last rule is Family Name (not matchoded) and City (not matchcoded).  Within the options we have told the clustering node to give us a True or false if a rule is matched.

![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Matching\Conditional by Match Type\img\conditional_match_clustering.jpg)

The final step in this job adds a little bit of EEL code so that we can look at the three condition flags and then turn the status into a English readable summary of which matching conditions were triggered within the cluster.

![Input Data](C:\temp\github\sas-dqdg-assets-github\SAS9\DataFlux Jobs\Matching\Conditional by Match Type\img\conditional_match_post_process.jpg)

![GITLAB Image](./img/Screenshot_1_2.jpg)




| Job Specifics    | Explanation                 |
| ---------------- | --------------------------- |
| Data Source      | DataFlux Sample \| Contacts |
| QKB Version      | CI33                        |
| DataFlux version | 2.10                        |

#### Change Log

------

Version 1.0 (10/09/2025)

- Initial Version