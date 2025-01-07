Login to AWS as admin

Create a New VM, with Amazon Linux Kernel 5.10 OS

allow https http ssh and 21 and create machine

select VM and under actions->instance Settings->Allow tags in instance metadata->Allow

select vm and under actions->instance Settings->Edit tags->add some tag name and value

goto amazon inspector

goto on demand scans

create new scan, give name->provide key and value we created in VM, 

Benchmark level is Level2

Target All Accounts

Schedule is One time scan->Create

Wait for scan to complete and see if you have any vulns under findings
