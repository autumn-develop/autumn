Autumn Project
================

Autumn is an **automation framework mobile solution** based on microservice architecture that provides powerful tools to take your automation work to the next level.  

Autumn makes it easy to create dynamic automation test suites that you can "just run".

We took the complexity of TestNG framework and made it simpler, so you can get started with the minimum fuss.  



Pillars
--
![Pillars](./docs/pillars.jpg?raw=true "Automation Pillars")





Features
--

- Generate project scaffolding by using [rpp-shopay-ms](http://rpp-shopay-ms.github.com) 
    - Same structure
    - OOP Inheritance
    - Common: you can share the **Common** automation scripts like Utils, Payloads and even Test Cases with your team with a repository [like this](http://link.to.rpp-automation-common)  
    - Single responsibility
    - Autonomy

- Continuous Integration / Continuous Delivery  
    - Quality Gates: to raise a sonarqube server in your organization, please refer to the [docs](https://docs.sonarqube.org/latest/setup/overview/)  
    - Versioning: Use the artifact repository of your preference
    - Automated suite administration.
    
- Dynamic suite creation (please refer to [rpp-eva-auto-qa-mf](http://link.to.eva.autoqa.com))
    - Tutti frutti test selection
    - Payload edition
    - Device selection & configuration

- Executions
    - Dynamic class loader: the automation scripts packages artifacts ".jar" could be loaded at runtime  
    - Centralized, distributed, external: executes your test cases wherever you want, [see details](http:details.about.execution-types.com) 
    - near Real time device detection
    
- Results (please refer to [rpp-eva-auto-qa-mf](http://link.to.eva.autoqa.com/results) for more details)
    - Logs: See the appium logs in real time 
    - Payload: See the payload data used in your test
    - Video recording: generate video evidence
    - PDF evidence: generate document evidence with screenshots to share later 
    

Global structure
--

- **Automation projects** = Test Cases
- **Suite** = automation projects
- **Configuration** = App package configuration and platforms
- **Suite execution** = Suites + configurations
- **Execution** = Suites executions


Backend Architecture
--
![Backend](./docs/backend.jpg?raw=true "Automation Pillars")


**Microservice Repositories**


- [rpp-auto-gateway-api](https://github.com/rappiinc/rpp-auto-gateway-api]): API entry point, all the API endpoints are consumed using this gateway. 
- [rpp-auto-test-ms](https://github.com/rappiinc/rpp-auto-test-ms): Run execution suites in devices.
- [rpp-auto-farm-hub-ms](https://github.com/rappiinc/rpp-auto-farm-hub-ms): Manage distributed devices in farm hub. 
- [rpp-auto-executor-or](https://github.com/rappiinc/rpp-auto-executor-or): Manages all the actions flows and interactions in the Autumn API.
- [rpp-auto-execution-ms](https://github.com/rappiinc/rpp-auto-execution-ms): Stores executed suites registry and provide information related to the current execution suites.
- [rpp-auto-suite-execution-ms](https://github.com/rappiinc/rpp-auto-suite-execution-ms): Stores the suites with their execution configuration (capabilities and devices). 
- [rpp-auto-queue-ms](https://github.com/rappiinc/rpp-auto-queue-ms): Queue/dequeue execution suites managed by the orchestrator MS (`rpp-auto-executor-or`).
- [rpp-auto-results-ms](https://github.com/rappiinc/rpp-auto-results-ms): Store automation execution suites results in S3 buckets & sends results notification to Slack channel.
- [rpp-auto-capabilities-ms](https://github.com/rappiinc/rpp-auto-capabilities-ms): Stores multiple Appium capabilities  & app URLs to configure the "exeuction" of execution suites.
- [rpp-auto-testcase-ms](https://github.com/rappiinc/rpp-auto-testcase-ms): Stores automation project metadata definition including: test cases, default payload data and repository details in JSON format.
- [rpp-auto-suite-ms](https://github.com/rappiinc/rpp-auto-suite-ms): Stores automation suites composed by n automation projects.
- [rpp-auto-configuration-ms](https://github.com/rappiinc/rpp-auto-configuration-ms): Manage general configurations related with Slack & TM4J.



**Libraries Repositories**


- [bitbucket-api-client-lib](https://github.com/rappiinc/bitbucket-api-client-lib): Code against the Bitbucket API to automate simple tasks, embed Bitbucket data into your own site, build mobile or desktop apps, or even add custom UI add-ons into Bitbucket itself using the Connect framework.
- [tm4j-api-client-lib](https://github.com/rappiinc/tm4j-api-client-lib): Test Management for Jira Cloud API  version: 2
- [rpp-automation-commons-lib](https://github.com/rappiinc/rpp-automation-commons-lib): This library encapsulates the common dtos and classes for the autumn solution.
- [rpp-api-response-handler-lib](https://github.com/rappiinc/rpp-api-response-handler-lib): This library helps to manage exceptions in MS's and return the appropriate error message.
- [testng-classloader-lib](https://github.com/rappiinc/testng-classloader-lib): This artifact helps to load jar files into org.testng.internal.ClassHelper it helps to execute automation scripts at runtime

- [rpp-automation-ci-cd-lib](https://github.com/rappiinc/rpp-automation-ci-cd-lib): This artifact helps to package automation scripts into jars files, also register the automation project metadata in `rpp-auto-testcase-ms`
- [rpp-automation-common](https://github.com/rappiinc/rpp-automation-common): This project has the template structure to work with the solution, contains the main classes to execute  your automation test scripts, it helps to share useful automation scripts and utilities with the team.


**Wiki**

Please checkout the [wiki](https://github.com/autumn-develop/autumn/wiki) to have a happy onboarding.

**Credits**

Special thanks to [Juan Carlos Duarte](https://github.com/autumn-develop), [Mario Teran](https://github.com/marte876) and [Miguel Cervantes](https://github.com/Ingenator)

## License

Autumn is Open Source software released under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0).


