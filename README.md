
# Test case Manual file

This file describes the keywords used in the test case yaml file.



##### Table of Contents  
[Gobal Keywords](#global)  
[Testcase Keywords](#testcase)
[Teststep Keywords](#teststep)
[input keywords](#input)
[params keywords](#params)
[expected keywords](#expected)



<a name="global"/>
## Gobal Keywords

| Keyword | Can be overriden | Purpose | Mandatory/Optional |
|-----------------|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|
| target | At test case and step level | define the target or DUT from testbed YML which will be used by driver to execute commands, or API on | Mandatory |
| cache_responses | N.A | Defines it as true, responses under a testcase will be cached. If cached it will be available as responseList.Define it as false, response under a testcase will not be cached. | Optional |
| driver | test case and step level | | Optional |
| auto_cleanup | At test case level. | Automatically cleans up the created objects after the test case is executed. the flag can be disabled if the test step has explicit DELETE operations. | Mandatory. |

<a name="testcase"/>
## Testcase Keywords

| Keyword | Can be overriden | Purpose | Mandatory/Optional |
|--------------|---------------------------------|--------------------------------------------------------------------------------------------------------------------|--------------------|
| tims_id | At test case level only | TIMS test case id | Mandatory |
| name | At test case level only | name of the test case. Its mandatory & it will come in the report. | Mandatory |
| description | At test case level only | A brief about the test case. | Mandatory |
| group | At test case level only | Grouping of the test cases. | Mandatory. |
| auto_cleanup | Default takes the global value. | Override to not record the created objects. User needs to explicitly do a DELETE operation for the created objects | Optional |
| steps | N.A | Start of the Test cases. | Mandatory |

<a name="teststep"/>
## Teststeps keywords

| Keyword | Can be overridden | Generic/Driver Specific | Purpose | Mandatory/ Optional |
|----------|------------------------------|-------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| target | Yes, At the test step level. | Generic | If not specified it will be picked from global level or if specified at step level than that will be used. | Optional |
| driver | Yes, At the test step level. | | | Optional. Default REST |
| method | N.A | Generic | In general Method name could be CREATE,LIST,UPDATE,DELETE. Please see the Driver specific methods like python method.. Etc. | Mandatory |
| type | N.A | REST driver specific | URL or method name defined as per the respective resource.yaml file. | Mandatory |
| input | N.A | Generic | To pass the input parameters to the URL or payload. See the Input Keyword section. | Optional. Only required when the test case has input. |
| expected | N.A | Generic | To pass the expected response data and status code for the test step. | Mandatory |


<a name="input"/>
### input keywords

 
| Keyword | Can be overridden | Generic/Driver Specific | Purpose | Mandatory/ Optional |
|----------|------------------------------|-------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| params | N.A | Generic | Provide a parameters to URL or payload | Optional. |
| query_param | N.A | REST Driver | To pass query parameters to the URL.example limit=1000 | Optional |
| request_data | N.A | Generic | Payload for the operation goes here. | |

<a name="params"/>
#### params keywords


| Keyword | Can be overridden | Generic/Driver Specific | Purpose | Mandatory/ Optional |
|----------|------------------------------|-------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| container-id | N.A | REST Driver | To pass the continer-id in the URL | Optional |
| domain_Global | Yes, at the Step level. | REST Driver | Default takes the Global value. Override to run the step on different domain. | Optional |
| id | N.A | REST Driver | To pass the id value in the URL | Optional |

<a name="expected"/>
### expected keywords


| Keyword | Can be overridden | Generic/Driver Specific | Purpose | Mandatory/ Optional |
|----------|------------------------------|-------------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| status | N.A | Generic | checking for the response status code. | Mandatory |
| response_data | N.A | Generic | Check for response content matching. | Optional |
























