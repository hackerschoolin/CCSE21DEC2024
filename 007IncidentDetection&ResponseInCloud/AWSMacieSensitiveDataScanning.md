Create a vuln bucket

Create a CSV file with 

```csv
CreditCardNumber,CVV,PIN
8613546813584161,811,1535
3216813516813525,896,3521
3513581361851385,369,3626
8461835686548644,565,6513
```

save the file and upload to your vuln bucket->make the bucket publicly accessible

Goto Macie,

Goto Jobs->Create->Select Buckets->COnfirm Buckets->Pick One Time Schedule->Goto Custom->
Specific and Search for Credit Card Details->Next->Next->Next->Give Job Name and Start
