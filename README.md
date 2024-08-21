[comment]: # "Auto-generated SOAR connector documentation"
# KnowThyCustomer

Publisher: Phantom  
Connector Version: 1.0.8  
Product Vendor: KnowThyCustomer  
Product Name: KnowThyCustomer  
Product Version Supported (regex): ".\*"  
Minimum Product Version: 3.0.251  

This app integrates with the KnowThyCustomer service to implement investigative actions

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a KnowThyCustomer asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**api_key** |  required  | password | API Key

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

You can enter any of the following valid combinations to generate a person report:<ul><li>first_name, last_name, address</li><li>first_name, last_name, phone</li><li>first_name, last_name, address, phone</li><li>bvid</li></ul>If <b>bvid</b> is provided, the rest of the inputs are ignored. The remaining parameters act as additional helper information if the other criteria do not produce a match or if multiple matches occur. They could also be used to disambiguate. For example, if George Clooney Sr. and George Clooney Jr. live at the same address, the <b>phone</b> parameter could be used to differentiate between the two.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**first_name** |  optional  | First Name | string | 
**last_name** |  optional  | Last Name | string | 
**address** |  optional  | Address | string | 
**phone** |  optional  | Phone | string |  `phone` 
**bvid** |  optional  | Person Unique Identifier | string |  `ktc user id` 

#### Action Output
DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.first_name | string |  |   Charles 
action_result.parameter.last_name | string |  |   Xavier 
action_result.parameter.address | string |  |   1407 Graymalkin Lane, North Salem, NY 10560 
action_result.parameter.phone | string |  `phone`  |   5101112222 
action_result.parameter.bvid | string |  `ktc user id`  |   N_MDM1Nag7OTrRlll5 
action_result.status | string |  |   success  failed 
action_result.message | string |  |     Parameter combination validations failed. Please see the action documentation to get a list of valid parameter validations  User found: True  User found: False 
summary.total_objects | numeric |  |   1 
summary.total_objects_successful | numeric |  |   1  0 
action_result.data.\*.addresses.\*.full | string |  |   1407 Graymalkin Lane, North Salem, NY 10560 
action_result.data.\*.addresses.\*.property_record_available | boolean |  |   True  False 
action_result.data.\*.addresses.\*.precision | string |  |   zip9 
action_result.data.\*.addresses.\*.longitude | numeric |  |   -73.57190509999998 
action_result.data.\*.addresses.\*.parts.city | string |  |   North Salem 
action_result.data.\*.addresses.\*.parts.post_direction | string |  |    
action_result.data.\*.addresses.\*.parts.zip | string |  |   10560 
action_result.data.\*.addresses.\*.parts.house_number | string |  |   1407 
action_result.data.\*.addresses.\*.parts.country | string |  |   US   
action_result.data.\*.addresses.\*.parts.street_name | string |  |   Graymalkin 
action_result.data.\*.addresses.\*.parts.pre_direction | string |  |    
action_result.data.\*.addresses.\*.parts.state | string |  |   NY 
action_result.data.\*.addresses.\*.parts.street_type | string |  |   Ln 
action_result.data.\*.addresses.\*.parts.unit | string |  |    
action_result.data.\*.addresses.\*.parts.zip4 | string |  |   1962 
action_result.data.\*.addresses.\*.latitude | numeric |  |   41.3350356 
action_result.data.\*.addresses.\*.first_seen | string |  |   2000-01-01 
action_result.data.\*.addresses.\*.type | string |  |    
action_result.data.\*.addresses.\*.last_seen | string |  |   2017-11-11 
action_result.data.\*.phones.\*.first_seen | string |  |   2009-03-00  2017-05-00 
action_result.data.\*.phones.\*.type | string |  |    
action_result.data.\*.phones.\*.number | string |  `phone`  |   5101112222 
action_result.data.\*.phones.\*.country_code | numeric |  |   0 
action_result.data.\*.phones.\*.last_seen | string |  |   2013-07-00  2017-05-00 
action_result.data.\*.connections.neighbors.\*.addresses.\*.full | string |  |   1407 Graymalkin Lane, North Salem, NY 10560 
action_result.data.\*.connections.neighbors.\*.addresses.\*.property_record_available | boolean |  |   True  False 
action_result.data.\*.connections.neighbors.\*.addresses.\*.precision | string |  |   zip9 
action_result.data.\*.connections.neighbors.\*.addresses.\*.longitude | numeric |  |   -73.57190509999998 
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.city | string |  |   North Salem 
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.post_direction | string |  |    
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.zip | string |  |   10560 
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.house_number | string |  |   1407 
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.country | string |  |    
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.street_name | string |  |   Graymalkin 
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.pre_direction | string |  |    
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.state | string |  |   NY 
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.street_type | string |  |   Ln 
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.unit | string |  |    
action_result.data.\*.connections.neighbors.\*.addresses.\*.parts.zip4 | string |  |   1962 
action_result.data.\*.connections.neighbors.\*.addresses.\*.latitude | numeric |  |   41.3350356 
action_result.data.\*.connections.neighbors.\*.addresses.\*.first_seen | string |  |   2013-06-00  1996-09-00 
action_result.data.\*.connections.neighbors.\*.addresses.\*.type | string |  |    
action_result.data.\*.connections.neighbors.\*.addresses.\*.last_seen | string |  |   2017-08-00 
action_result.data.\*.connections.neighbors.\*.names.\*.first_seen | string |  |    
action_result.data.\*.connections.neighbors.\*.names.\*.full | string |  |  
action_result.data.\*.connections.neighbors.\*.names.\*.parts.salutation | string |  |    
action_result.data.\*.connections.neighbors.\*.names.\*.parts.first_name | string |  |  
action_result.data.\*.connections.neighbors.\*.names.\*.parts.last_name | string |  |  
action_result.data.\*.connections.neighbors.\*.names.\*.parts.middle_name | string |  |  
action_result.data.\*.connections.neighbors.\*.names.\*.parts.suffix | string |  |    
action_result.data.\*.connections.neighbors.\*.names.\*.last_seen | string |  |    
action_result.data.\*.connections.neighbors.\*.first_seen | string |  |    
action_result.data.\*.connections.neighbors.\*.id | string |  |   N_MDPlNzA4QzY2OSk4 
action_result.data.\*.connections.neighbors.\*.last_seen | string |  |    
action_result.data.\*.connections.neighbors.\*.ages | numeric |  |   42 
action_result.data.\*.connections.neighbors.\*.dobs | string |  |   1970-12-13 
action_result.data.\*.connections.relatives.\*.addresses.\*.full | string |  |  
action_result.data.\*.connections.relatives.\*.addresses.\*.property_record_available | boolean |  |   True  False 
action_result.data.\*.connections.relatives.\*.addresses.\*.precision | string |  |   zip9 
action_result.data.\*.connections.relatives.\*.addresses.\*.longitude | numeric |  |  
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.city | string |  |  
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.post_direction | string |  |    
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.zip | string |  |  
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.house_number | string |  |  
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.country | string |  |    
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.street_name | string |  |  
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.pre_direction | string |  |    
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.state | string |  |   CA 
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.street_type | string |  |  
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.unit | string |  |    
action_result.data.\*.connections.relatives.\*.addresses.\*.parts.zip4 | string |  |   1962 
action_result.data.\*.connections.relatives.\*.addresses.\*.latitude | numeric |  |  
action_result.data.\*.connections.relatives.\*.addresses.\*.first_seen | string |  |   2016-10-00  2006-08-00 
action_result.data.\*.connections.relatives.\*.addresses.\*.type | string |  |    
action_result.data.\*.connections.relatives.\*.addresses.\*.last_seen | string |  |   2016-10-00  2017-05-00 
action_result.data.\*.connections.relatives.\*.last_cohabitate | string |  |   2017-09-00 
action_result.data.\*.connections.relatives.\*.names.\*.first_seen | string |  |    
action_result.data.\*.connections.relatives.\*.names.\*.full | string |  |  
action_result.data.\*.connections.relatives.\*.names.\*.parts.salutation | string |  |    
action_result.data.\*.connections.relatives.\*.names.\*.parts.first_name | string |  |  
action_result.data.\*.connections.relatives.\*.names.\*.parts.last_name | string |  |  
action_result.data.\*.connections.relatives.\*.names.\*.parts.middle_name | string |  |  
action_result.data.\*.connections.relatives.\*.names.\*.parts.suffix | string |  |    
action_result.data.\*.connections.relatives.\*.names.\*.last_seen | string |  |    
action_result.data.\*.connections.relatives.\*.first_seen | string |  |    
action_result.data.\*.connections.relatives.\*.id | string |  |  
action_result.data.\*.connections.relatives.\*.last_seen | string |  |    
action_result.data.\*.images.\*.url | string |  `url`  |  
action_result.data.\*.images.\*.source | string |  |    
action_result.data.\*.images.\*.thumb | string |  `url`  |  
action_result.data.\*.images.\*.confidence_score | numeric |  |   25 
action_result.data.\*.names.\*.first_seen | string |  |    
action_result.data.\*.names.\*.full | string |  |   CHARLES XAVIER 
action_result.data.\*.names.\*.parts.salutation | string |  |    
action_result.data.\*.names.\*.parts.first_name | string |  |   CHARLES 
action_result.data.\*.names.\*.parts.last_name | string |  |   XAVIER 
action_result.data.\*.names.\*.parts.middle_name | string |  |    
action_result.data.\*.names.\*.parts.suffix | string |  |    
action_result.data.\*.names.\*.last_seen | string |  |    
action_result.data.\*.usernames.\*.username | string |  `user name`  |   charles.xavier 
action_result.data.\*.usernames.\*.first_seen | string |  |   2000-12-13 
action_result.data.\*.usernames.\*.last_seen | string |  |    
action_result.data.\*.languages.\*.region | string |  |   US 
action_result.data.\*.languages.\*.language | string |  |   en 
action_result.data.\*.report_info.response_time | numeric |  |   1.072886623  4.668284976  0.104992071 
action_result.data.\*.report_info.report_id | string |  |   1823592a-2cff-467a-9053-ce0c8f451b7b 
action_result.data.\*.jobs.\*.industry | string |  |    
action_result.data.\*.jobs.\*.title | string |  |   Principal 
action_result.data.\*.jobs.\*.company | string |  |   X-Men 
action_result.data.\*.jobs.\*.period.start | string |  |    
action_result.data.\*.jobs.\*.period.end | string |  |    
action_result.data.\*.user_ids.\*.first_seen | string |  |   2000-12-19 
action_result.data.\*.user_ids.\*.user_id | string |  |   11111111@linkedin 
action_result.data.\*.user_ids.\*.last_seen | string |  |    
action_result.data.\*.emails.\*.email_address | string |  `email`  |   charles@xavier.com 
action_result.data.\*.emails.\*.is_disposable | boolean |  |   True  False 
action_result.data.\*.emails.\*.address_md5 | string |  `md5`  |    
action_result.data.\*.emails.\*.first_seen | string |  |     2012-03-30 
action_result.data.\*.emails.\*.type | string |  |   personal   
action_result.data.\*.emails.\*.is_public_provider | boolean |  |   True  False 
action_result.data.\*.emails.\*.last_seen | string |  |     2017-09-21 
action_result.data.\*.gender | string |  |   male   
action_result.data.\*.social.\*.category | string |  |   personal_profiles   
action_result.data.\*.social.\*.bio | string |  |    
action_result.data.\*.social.\*.domain | string |  `domain`  |   facebook.com   
action_result.data.\*.social.\*.url | string |  `url`  |   http://facebook.com/people/_/100000111111111 
action_result.data.\*.social.\*.source | numeric |  |   2 
action_result.data.\*.social.\*.sponsored | boolean |  |   True  False 
action_result.data.\*.social.\*.type | string |  |   facebook 
action_result.data.\*.bvids | string |  |   N_MTB5MjUqMTI4ORQ1 
action_result.data.\*.ages | numeric |  |   23 
action_result.data.\*.connections.relatives.\*.phones.\*.first_seen | string |  |    
action_result.data.\*.connections.relatives.\*.phones.\*.type | string |  |    
action_result.data.\*.connections.relatives.\*.phones.\*.number | string |  |   51000002222 
action_result.data.\*.connections.relatives.\*.phones.\*.country_code | numeric |  |   0 
action_result.data.\*.connections.relatives.\*.phones.\*.last_seen | string |  |    
action_result.data.\*.connections.relatives.\*.ages | numeric |  |   61 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.full | string |  |  
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.property_record_available | boolean |  |   True  False 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.precision | string |  |   zip9 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.longitude | numeric |  |   -73.57190509999998 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.city | string |  |  
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.post_direction | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.zip | string |  |   91784 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.house_number | string |  |   1000 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.country | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.street_name | string |  |   25th 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.pre_direction | string |  |   W 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.state | string |  |   NY 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.street_type | string |  |   St 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.unit | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.parts.zip4 | string |  |   1572 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.latitude | numeric |  |   41.3350356 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.first_seen | string |  |   1993-01-00 
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.type | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.addresses.\*.last_seen | string |  |   2015-12-00 
action_result.data.\*.connections.relatives.\*.relatives.\*.last_cohabitate | string |  |   2017-06-00 
action_result.data.\*.connections.relatives.\*.relatives.\*.phones.\*.first_seen | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.phones.\*.type | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.phones.\*.number | string |  |   5102223333 
action_result.data.\*.connections.relatives.\*.relatives.\*.phones.\*.country_code | numeric |  |   0 
action_result.data.\*.connections.relatives.\*.relatives.\*.phones.\*.last_seen | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.ages | numeric |  |   86 
action_result.data.\*.connections.relatives.\*.relatives.\*.names.\*.first_seen | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.names.\*.full | string |  |  
action_result.data.\*.connections.relatives.\*.relatives.\*.names.\*.parts.salutation | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.names.\*.parts.first_name | string |  |  
action_result.data.\*.connections.relatives.\*.relatives.\*.names.\*.parts.last_name | string |  |  
action_result.data.\*.connections.relatives.\*.relatives.\*.names.\*.parts.middle_name | string |  |  
action_result.data.\*.connections.relatives.\*.relatives.\*.names.\*.parts.suffix | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.names.\*.last_seen | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.dobs | string |  |   1931-08-28 
action_result.data.\*.connections.relatives.\*.relatives.\*.first_seen | string |  |    
action_result.data.\*.connections.relatives.\*.relatives.\*.id | string |  |  
action_result.data.\*.connections.relatives.\*.relatives.\*.last_seen | string |  |    
action_result.data.\*.connections.relatives.\*.dobs | string |  |  
action_result.data.\*.dobs | string |  |   1994-10-25 
action_result.summary.user_found | boolean |  |   True  False 