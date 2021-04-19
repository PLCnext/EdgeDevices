## Quick Reference Guide<br>
### For
## Phoenix Contact: EPC 1522 and EPC 1502
 
### Version: 1.2
---
# Any-Cloud to OPC UA

This flow is used for writing the data into OPCUA server from cloud (Azure/AWS/GCP). Below flow is used for explaining the said workflow:

![CloudToOPC](images/06_CloudToOPC.JPG) <br>
SourceCode: [AnyCloud to OPC UA](SourceCode/Quickstart_Flows/QuickGuideFlows/Cloud_to_OPCUA.json)
## Configuration and Steps

There are two function nodes are used with Pub Sub node and OPCUA Client Node, for writing values into OPCUA.

__Configure Pub Sub node__
- Configure Pub Sub node with credentials, Key File, Subscription with respect to GCP cloud configuration.
![PubSubConfig](images/06_PubSubConfig.JPG) <br>

__Configure Function nodes__
Configure respective function nodes with respect to OPCUA Server configuration as given below: 
>msg.topic="ns=4;s=Arp.Plc.Eclr/Sint1;datatype=SByte"; <br>
return msg;

__Configure OPCUA Client node__
- Configure OPCUA Client node properties with Endpoint, Action (Write), Certificate.
- Configure Credentials with End Point and Security Policy and Security Mode in OPCUA Client Properties.

## Data on OPC UA Client
After the data is triggered from GCP cloud, it can be seen under Data Access View of OPCUA client for the respective address location like below: <br>

![Example_DataOnClient](images/06_DataOnClient.JPG) <br>

