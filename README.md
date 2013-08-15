arch-poc
========

Getting started with the HAAG infrastructure POCs
This set of proofs of concept are intended to illustrate partial implementations of two HUIT
Enterprise Architecure design patterns using Amazon Web Services (AWS) technology.

The first shows a common three tiered architecture that has scalable front end servers that takes
reqests from the outside world and forwards them to backend servers that in turn use one or more of
several persistence layers. The second illustrates creation of parts of a development and test 
environment.  For more details on the Proofs of Concept, use cases, design patterns and AWS technologies
used in these POCs, see the HUIT Enterprise Architecture Web Site.  The home page is located at:

     https://wikis.fas.harvard.edu/huitarch/HUIT_Enterprise_Architecture

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
4. setup python env and requirements 
    *  export PYTHONPATH=~/git/nepho:$PYTHONPATH
 * python 2.6 or newer
 * boto
 * awscli
 * jinja2
 * pyyaml
5. install pip (easy install pip / homebrew)
5. install boto
7. script for creating 3 tier app via cloudformation
  * clones hu-python in location
  * install dev env (hu with different args)

Test to see if things are working:
 ./bin/nepho -E development show-template simple-website

Validate Template 
./bin/nepho -E development validate-template simple-website

Deploy
./bin/nepho -E development deploy simple-website 

However you need to change the ssh keys

nepho/deployments/simple-website.yaml needs to be set to your keys

to delete a deployment:
 ./bin/nepho -E development delete simple-website 

8. Cloudwatch monitoring
9. Script to kill stuff (hu destroy)

General references on the arch website for AWS


TH Notes
nepho/drivers/aws/puppet-snippet.sh (puppet handoff) 
