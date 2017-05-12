# github.repo.com
Synopsis

This application will dynamically stop the mule process if there is any error and start the mule process at runtime without any deployment.

Code Example

<scripting:component doc:name="Groovy">
                    <scripting:script engine="Groovy"><![CDATA[if(muleContext.registry.lookupFlowConstruct(flowVars.demoStartFlow).isStarted() && demo.test.isdb.stop=='true')
{
muleContext.registry.lookupFlowConstruct(flowVars.demoStartFlow).stop();
flowVars.pubSuspendstatus=flowVars.demoStartFlow+' Suspended now ';
}
else
{
flowVars.pubSuspendstatus='Process already suspended';
}]]></scripting:script>
                </scripting:component>

Motivation

This provide the facility to the developer to stop the process if there is any error realted to end point and data base apart from that you can start the process without and redeployment once the issue is resolved.

Installation

You have to install Anypoint Studion and Active MQ and for the data base you have required MS SQL.

Tests
You can send a http request and stop the MSSQL server to generate the issue. if there  is any issue this will stop the process for testing purpose you can again hit the same url to check it that Mule Listner is active or not,post after you can send some message to JMS once the issue got resolved.This will start//restart the Mule stopped process.

License
Licenseis not required Anypoint studio and Active MQ is free.
