[comment]: # "Auto-generated SOAR connector documentation"
# KnowThyCustomer

Publisher: Phantom  
Connector Version: 1\.0\.6  
Product Vendor: KnowThyCustomer  
Product Name: KnowThyCustomer  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 3\.0\.251  

This app integrates with the KnowThyCustomer service to implement investigative actions

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a KnowThyCustomer asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**api\_key** |  required  | password | API Key

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[get user](#action-get-user) - Gets the attributes of a user  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'get user'
Gets the attributes of a user

Type: **investigate**  
Read only: **True**

You can enter any of the following valid combinations to generate a person report\:<ul><li>first\_name, last\_name, address</li><li>first\_name, last\_name, phone</li><li>first\_name, last\_name, address, phone</li><li>bvid</li></ul>If <b>bvid</b> is provided, the rest of the inputs are ignored\. The remaining parameters act as additional helper information if the other criteria do not produce a match or if multiple matches occur\. They could also be used to disambiguate\. For example, if George Clooney Sr\. and George Clooney Jr\. live at the same address, the <b>phone</b> parameter could be used to differentiate between the two\.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**first\_name** |  optional  | First Name | string | 
**last\_name** |  optional  | Last Name | string | 
**address** |  optional  | Address | string | 
**phone** |  optional  | Phone | string |  `phone` 
**bvid** |  optional  | Person Unique Identifier | string |  `ktc user id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.first\_name | string | 
action\_result\.parameter\.last\_name | string | 
action\_result\.parameter\.address | string | 
action\_result\.parameter\.phone | string |  `phone` 
action\_result\.parameter\.bvid | string |  `ktc user id` 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 
action\_result\.data\.\*\.addresses\.\*\.full | string | 
action\_result\.data\.\*\.addresses\.\*\.property\_record\_available | boolean | 
action\_result\.data\.\*\.addresses\.\*\.precision | string | 
action\_result\.data\.\*\.addresses\.\*\.longitude | numeric | 
action\_result\.data\.\*\.addresses\.\*\.parts\.city | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.post\_direction | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.zip | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.house\_number | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.country | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.street\_name | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.pre\_direction | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.state | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.street\_type | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.unit | string | 
action\_result\.data\.\*\.addresses\.\*\.parts\.zip4 | string | 
action\_result\.data\.\*\.addresses\.\*\.latitude | numeric | 
action\_result\.data\.\*\.addresses\.\*\.first\_seen | string | 
action\_result\.data\.\*\.addresses\.\*\.type | string | 
action\_result\.data\.\*\.addresses\.\*\.last\_seen | string | 
action\_result\.data\.\*\.phones\.\*\.first\_seen | string | 
action\_result\.data\.\*\.phones\.\*\.type | string | 
action\_result\.data\.\*\.phones\.\*\.number | string |  `phone` 
action\_result\.data\.\*\.phones\.\*\.country\_code | numeric | 
action\_result\.data\.\*\.phones\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.full | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.property\_record\_available | boolean | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.precision | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.longitude | numeric | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.city | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.post\_direction | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.zip | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.house\_number | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.country | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.street\_name | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.pre\_direction | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.state | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.street\_type | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.unit | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.parts\.zip4 | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.latitude | numeric | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.type | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.addresses\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.names\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.names\.\*\.full | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.names\.\*\.parts\.salutation | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.names\.\*\.parts\.first\_name | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.names\.\*\.parts\.last\_name | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.names\.\*\.parts\.middle\_name | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.names\.\*\.parts\.suffix | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.names\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.id | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.ages | numeric | 
action\_result\.data\.\*\.connections\.neighbors\.\*\.dobs | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.full | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.property\_record\_available | boolean | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.precision | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.longitude | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.city | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.post\_direction | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.zip | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.house\_number | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.country | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.street\_name | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.pre\_direction | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.state | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.street\_type | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.unit | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.parts\.zip4 | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.latitude | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.type | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.addresses\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.last\_cohabitate | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.names\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.names\.\*\.full | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.names\.\*\.parts\.salutation | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.names\.\*\.parts\.first\_name | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.names\.\*\.parts\.last\_name | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.names\.\*\.parts\.middle\_name | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.names\.\*\.parts\.suffix | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.names\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.id | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.last\_seen | string | 
action\_result\.data\.\*\.images\.\*\.url | string |  `url` 
action\_result\.data\.\*\.images\.\*\.source | string | 
action\_result\.data\.\*\.images\.\*\.thumb | string |  `url` 
action\_result\.data\.\*\.images\.\*\.confidence\_score | numeric | 
action\_result\.data\.\*\.names\.\*\.first\_seen | string | 
action\_result\.data\.\*\.names\.\*\.full | string | 
action\_result\.data\.\*\.names\.\*\.parts\.salutation | string | 
action\_result\.data\.\*\.names\.\*\.parts\.first\_name | string | 
action\_result\.data\.\*\.names\.\*\.parts\.last\_name | string | 
action\_result\.data\.\*\.names\.\*\.parts\.middle\_name | string | 
action\_result\.data\.\*\.names\.\*\.parts\.suffix | string | 
action\_result\.data\.\*\.names\.\*\.last\_seen | string | 
action\_result\.data\.\*\.usernames\.\*\.username | string |  `user name` 
action\_result\.data\.\*\.usernames\.\*\.first\_seen | string | 
action\_result\.data\.\*\.usernames\.\*\.last\_seen | string | 
action\_result\.data\.\*\.languages\.\*\.region | string | 
action\_result\.data\.\*\.languages\.\*\.language | string | 
action\_result\.data\.\*\.report\_info\.response\_time | numeric | 
action\_result\.data\.\*\.report\_info\.report\_id | string | 
action\_result\.data\.\*\.jobs\.\*\.industry | string | 
action\_result\.data\.\*\.jobs\.\*\.title | string | 
action\_result\.data\.\*\.jobs\.\*\.company | string | 
action\_result\.data\.\*\.jobs\.\*\.period\.start | string | 
action\_result\.data\.\*\.jobs\.\*\.period\.end | string | 
action\_result\.data\.\*\.user\_ids\.\*\.first\_seen | string | 
action\_result\.data\.\*\.user\_ids\.\*\.user\_id | string | 
action\_result\.data\.\*\.user\_ids\.\*\.last\_seen | string | 
action\_result\.data\.\*\.emails\.\*\.email\_address | string |  `email` 
action\_result\.data\.\*\.emails\.\*\.is\_disposable | boolean | 
action\_result\.data\.\*\.emails\.\*\.address\_md5 | string |  `md5` 
action\_result\.data\.\*\.emails\.\*\.first\_seen | string | 
action\_result\.data\.\*\.emails\.\*\.type | string | 
action\_result\.data\.\*\.emails\.\*\.is\_public\_provider | boolean | 
action\_result\.data\.\*\.emails\.\*\.last\_seen | string | 
action\_result\.data\.\*\.gender | string | 
action\_result\.data\.\*\.social\.\*\.category | string | 
action\_result\.data\.\*\.social\.\*\.bio | string | 
action\_result\.data\.\*\.social\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.social\.\*\.url | string |  `url` 
action\_result\.data\.\*\.social\.\*\.source | numeric | 
action\_result\.data\.\*\.social\.\*\.sponsored | boolean | 
action\_result\.data\.\*\.social\.\*\.type | string | 
action\_result\.data\.\*\.bvids | string | 
action\_result\.data\.\*\.ages | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.phones\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.phones\.\*\.type | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.phones\.\*\.number | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.phones\.\*\.country\_code | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.phones\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.ages | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.full | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.property\_record\_available | boolean | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.precision | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.longitude | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.city | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.post\_direction | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.zip | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.house\_number | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.country | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.street\_name | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.pre\_direction | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.state | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.street\_type | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.unit | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.parts\.zip4 | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.latitude | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.type | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.addresses\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.last\_cohabitate | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.phones\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.phones\.\*\.type | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.phones\.\*\.number | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.phones\.\*\.country\_code | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.phones\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.ages | numeric | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.names\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.names\.\*\.full | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.names\.\*\.parts\.salutation | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.names\.\*\.parts\.first\_name | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.names\.\*\.parts\.last\_name | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.names\.\*\.parts\.middle\_name | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.names\.\*\.parts\.suffix | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.names\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.dobs | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.first\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.id | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.relatives\.\*\.last\_seen | string | 
action\_result\.data\.\*\.connections\.relatives\.\*\.dobs | string | 
action\_result\.data\.\*\.dobs | string | 
action\_result\.summary\.user\_found | boolean | 