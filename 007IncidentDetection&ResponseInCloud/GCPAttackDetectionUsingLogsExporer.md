Enable Cloud Function API in GCP

Create->Helloworld Name->Region Default->https trigger

allow unauthenticated invocations under authentication

expand run time, set max autoscaling machines are 5->Deploy

take the url and try to access

open a cloud shell

download vegeta 

`wget https://github.com/tsenart/vegeta/releases/download/v12.12.0/vegeta_12.12.0_linux_386.tar.gz`

extract 
`tar xfz vegeta_12.12.0_linux_386.tar.gz`

`echo "GET URL OF YOUR CLOUD FUCNTION" | ./vegeta attack -duration=300s > results.txt`

in a new tab goto logs explorer(search for that)->Apply Filter to select your cloud Function API link->should be able see logs
