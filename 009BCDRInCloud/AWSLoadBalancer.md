Create a VPC use ip range 10.0.0.0/16

Create 2 subnets with 10.0.10.0/24 10.0.20.0/24 as ipranges, and use different availability zones for both subnets

Create  VM with that VPC

After VM is successfully created

goto LoadBalancing->TargetGroups->Create->Instances->GiveName->Select YourVPC->Next->Select YourVM, Include As pending below->Create

goto LoadBalancing->LoadBalancers->Create->ApplicationLoadBalancer->GiveName->InternalSchme->Pick The Created VPC->Check Both of your Mappings->Pick the target group created under Listeners and Routing->Create Load Balancer.
