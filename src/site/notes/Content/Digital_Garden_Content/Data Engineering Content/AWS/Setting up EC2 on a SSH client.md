---
{"dg-publish":true,"permalink":"/content/digital-garden-content/data-engineering-content/aws/setting-up-ec-2-on-a-ssh-client/","created":"2025-02-22T22:23:13.817+05:30","updated":"2025-04-08T18:26:54.892+05:30"}
---

#fundamentals #aws

## Steps to take 

>[!important]
>When setting up the key pair on your local machine, make sure you save it in a safe directory and add the path like so to the `SSH` command: e.g. `ssh -i /Users/Ethan/Documents/key-pairs/SSH-TEST.pem" ec2-user@ec2-13-48-67-243.eu-north-1.compute.amazonaws.com`  - This is an example for a AWS linux based EC2 instance 

1. Setup a basic EC2 instance with an AWS based OS
2. Ensure that the `key-pair` is eligible for SSH based connections by selecting the related option
3. Then go ahead and start your instance
4. After doing so, click on your instance ID and select the connect option
5. After doing so go to the SSH client tab and carry out the mentioned functions in the page
	1. **TO RUN THE `CHMOD` FUNCTION SIMPLY DO SO ON GIT BASH IN THE RELATED DIRECTORY**
	2. Use proper paths as well
6. Utilize VS code for your SSH client and then go ahead and paste in a command like this (the following is mostly applicable to a AWS linux based instance as the default username is `ec2-user`)

```bash
ssh -i /{path to key-pair}{key-pair name}.pem" {username}@{Public IPv4 DNS}
```

To quickly log in existing session, regard the following code:

```bash
ssh -i /Users/Ethan/Documents/key-pairs/SSH-TEST.pem ec2-user@ec2-13-60-9-127.eu-north-1.compute.amazonaws.com
```

Thereafter, to load into the `.venv` using AWS linux regard the following command:

```bash
source {envrionment_name}/bin/activate
```

```bash
ssh -i /Users/Ethan/Documents/key-pairs/SSH-TEST.pem ec2-user@ec2-13-61-142-229.eu-north-1.compute.amazonaws.com
```