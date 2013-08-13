arch-poc
========

Getting started with the HAAG infrastructure POCs

1. Pointer to readme 
2. aws credentials
>> this link help http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-set-up.html
>> Add something like this to your ~/.bash_profile file
>> export AWS_CONFIG_FILE=~/aws_creds.txt 
Your aws_creds.tx file should look something like this:
```Bash
[default]
aws_access_key_id=<KEY_ID>
aws_secret_access_key=<SECRET ACCESS KEY>
region=us-east-1
```
3. git clone arch-poc
4. setup python env
5. install pip (easy install pip / homebrew)
5. install boto
7. script for creating 3 tier app via cloudformation
  * clones hu-python in location
  * install dev env (hu with different args)
8. Cloudwatch monitoring
9. Script to kill stuff (hu destroy)

General references on the arch website for AWS

