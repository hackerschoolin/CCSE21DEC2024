## Prepare Your Enterprice SSO In Azure

In Azure Create a User In Microsoft Entra ID

Click On Enterprice Applications Under Manager Under MicroSoftEntraID->New Application->Search for AWS->Install AWS Identity Center From EnterPrice Applications

Click On Manage Under AWS Identity Center->Single Sign-On-> Change From Disabled to SAML

## Prepare Your AWS for External Identity Provider

In AWS Goto IAM IdentityCenter->Settings->Under Identity Source->Actions->Change Identity Source->Pick External Identity Provider->Download the Meta Data File

## Provide AWS IDP details in Azure

Upload that Metadata File->and Submit->and Download Federation MetadataXML file from Azure.

## Provide Azure Federation Details in AWS

In AWS upload Federation Metadata XML file under "IdP SAML metadata"->Next->Type ACCEPT->Change Identity Source

After the process is done, you will see notifications -> enable automatic provision -> copy the end point URL and access token and save them, example below

> https://scim.us-east-1.amazonaws.com/f3vc9332adf-2e0d-4d98-9ff0-efcbeb0429af/scim/v2

> e6f21e7e453-4067-27c-0d3af0ebab2f:5cf20109-31aa-4cd2-82e6-8d2cd250b6b5:AiUshwp3OppHxB5kRAKToXWWp7MgchzTX6hJQ7k7

Goto your AWS IAM Identity Center app in Azure, Add User, goto provisioning-> Pick Automatic Provisioning, and provide the above details->save->start Provision->wait for sometime for provisioning to complete.

after some time goto aws under "identity center" users you should be able to see your user

goto permission sets, and create permission sets according to your need

you can goto AWS and check users and also add permissions from permission sets like below

goto AWS accounts->Check the box under your account->Assign users or groups->select your user and save.
