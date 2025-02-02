Create a policy that only allows s3 activity within a region
> LoginAWS->IAM->Policies->Create->Service is s3->All Actions Allowed->All Resources->

> Expand Request Condition->Add ANother->Condition key is aws:RequestedRegion, QUalifier is StringEquals, Operator is us-east-1->Add COndition->save

Create a group
Create a user in that group
and attach the policy to that group.


if the user logs in, he should only be able to create a bucket within the specified region.

try to login to that account in a private window 
and check if you can do any s3 action outside of pre defined region.
