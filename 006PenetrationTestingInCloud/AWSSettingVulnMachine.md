## Create a new VM with below options
OS Ubuntu->HDD 30GB->ALLOW ssh,http,https->CREATE a key and download->launch Instance

Click On Security of the machine->Click on Securtity Groups->Edit InboundRules->AddRule->Custom TCP->21->IPV4Anywhere->Save

## Once machine is ready to connect

```bash
ssh -i keyfilename.pem ubuntu@IP

sudo -i

adduser USERNAME #fill details to create a new user with new weak password
apt update -y;apt install apache2 vsftpd -y
service apache2 start

nano /etc/ssh/sshd_config.d/60-cloudimg-settings.conf
#and change password authentication to YES
service ssh restart


nano /etc/vsftpd.conf #and look for below content and update them accordingly

anonymous_enable=YES
write_enable=YES
anon_upload_enable=YES
anon_mkdir_write_enable=YES

#after details are updated execute below command to start ftp server.
service vsftpd start
```
