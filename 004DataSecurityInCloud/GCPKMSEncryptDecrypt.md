Enable KMS

Open Key Management

Create new Key ring

give name give location(multiregion global) create

Create new key

give name, protection level software create


in gcloud shell

see list of projects
`gcloud projects list`

Select your project if many are there
`gcloud config set project [PROJECT_ID] (replace [PROJECT_ID] with your project ID)`

create a text file

echo "Data" > file.txt



`gcloud kms encrypt --location < location> --keyring < key ring name> --key < symmetric key name> --plaintext-file ./< text file name> --ciphertext-file ./< encrypted data text file name>`

In the above command, replace with the location of your key ring, < key ring name> with your key ring name, < symmetric key name> with the name of your symmetric key, < text file name> with the name of text file you created, and < encrypted data text file name> with a name for the encrypted file name with a .enc extension


`gcloud kms encrypt --key eccsecuritykey-new --keyring ecckey-new --location global --plaintext-file ./eccdata.txt --ciphertext-file ./eccdata.txt.enc`


`gcloud kms decrypt  --location < location>  --keyring < key ring name>  --key < key name>  --plaintext-file -  --ciphertext-file ./< encrypted text file name>`

In the above command, replace < location> with the location of your key ring, < key ring name> with your key ring name, < key name> with the name of your symmetric key, and < encrypted data text file name> with the name of the encrypted file with a .enc extension. For this lab, we have used the following command:


`gcloud kms decrypt --location global --keyring ecckey-new --key eccsecuritykey-new --plaintext-file - --ciphertext-file ./eccdata.txt.enc`

`gcloud kms keys versions create --location < location> --keyring < keyring name> --key < key name> --primary`


In the above command, replace with the location of your key ring, < keyring name> with your key ring name, and < key name> with the name of your symmetric key. In this lab, we have used the following command:

`gcloud kms keys versions create --location "global" --keyring "ecckey-new" --key "eccsecuritykey-new" --primary`

`gcloud kms keys versions disable "1" --location "" --keyring "" --key ""`

In the above command, replace with the location of your key ring, < keyring name> with your key ring name, and < key name> with the name of your symmetric key. In this lab, we have used the following command:

`gcloud kms keys versions disable "1" --location "global" --keyring "ecckey-new" --key "eccsecuritykey-new"`
