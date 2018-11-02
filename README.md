# sample-config-repo


cf login -a api.run.pivotal.io

Email>
Password>

cf push spring-helloworld-cf -p target\spring-helloworld-cf-0.0.1-SNAPSHOT.jar

cf logout

if getting below error while deploying.

The app cannot be mapped to route spring-helloworld-cf.cfapps.io because the rou
te exists in a different space, then run the below command

cf push *name of org in PWS* -p target/spring-helloworld-cf-0.0.1-SNAPSHOT.jar



To know name of your org execute below command
> cf target

> cf target -o myorg -s development


$ cf create-service -c '{"git": { "uri": "https://github.com/spring-cloud-samples/config-repo", "repos": { "cook": { "pattern": "cook*", "uri": "https://github.com/spring-cloud-services-samples/cook-config" } } }, "count": 3 }' p-config-server standard config-server
Creating service instance config-server in org myorg / space development as user...
OK

Create in progress. Use 'cf services' or 'cf service config-server' to check operation status.


Count parameter is to mention the number of nodes to provision: 1 by default, more for running in high-availability mode


$ cf service config-server
Showing info of service config-server in org myorg / space development as admin...

name:            config-server
service:         p-config-server
bound apps:
tags:
plan:            standard
description:     Config Server for Spring Cloud Applications
documentation:
dashboard:       https://spring-cloud-broker.apps.example.com/dashboard/p-config-server/c4d3feee-c3fb-49d6-881b-ff2eb822106b

Showing status of last operation from service config-server...

status:    create succeeded
message:
started:   2018-07-16T15:24:23Z
updated:   2018-07-16T15:25:27Z



cf create-service -c sampleJson.json p-config-server trial SampleConfigServer


cf update-service SampleConfigServer -c '{"git":{"uri": "https://github.com/enrkunal/configs","repos": {"sample": {"pattern": "sample*", "uri": "https://github.com/enrkunal/configs"}}},"count": 1}'

cf update-service SampleConfigServer -c sampleJson.json


