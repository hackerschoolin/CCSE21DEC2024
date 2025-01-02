Enable KMS

Open Key Management

Create new Key ring

give name give location(multiregion global) create

Create new key

give name, protection level software create

remember both names

## create a file and check file

nano verysecretdata.txt

## check file created or not

ls

## encrypt file
gcloud kms encrypt --location global --keyring CCSEDEC24 --key DataSecClass --plaintext-file ./verysecretdata.txt --ciphertext-file ./youcantreadthis.txt

## delete regular file to avoid data leaks
rm verysecretdata.txt 

## try reading encrypted file(should not be able to read)
cat youcantreadthis.txt 

## Decrypt to read the file again
gcloud kms decrypt --location global --keyring CCSEDEC24 --key DataSecClass --ciphertext-file ./youcantreadthis.txt --plaintext-file ./verysecretdata.txt

## Verify the file and read
ls
cat verysecretdata.txt 
