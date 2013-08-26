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

#### 1. Pointer to readme 

#### 2. AWS Credentials

This link will help 

- http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-set-up.html

Add something like this to your ~/.bash_profile file

    export AWS_CONFIG_FILE=~/.aws/aws_creds.txt

Your aws_creds.txt file should look something like this:

    [default]
    aws_access_key_id=<KEY_ID>
    aws_secret_access_key=<SECRET ACCESS KEY>
    region=us-east-1

It's best practice to restrict the permissions on this file, since this is your password
for AWS:

    chmod 600 ~/.aws/aws_creds.txt
    
#### 3. git clone arch-poc

#### 4. setup python env

* python 2.6 or newer

#### 5. Install rest of supporting environment

    pip easy_install pip
    pip install aswcli boto Jinja2 PyYAML

#### 6. sudo easy_install setuptools

    git clone https://github.com/huit/nepho
    cd nepho
    sudo python setup.py develop

Step 6 installs commands in your `/usr/local/bin/nepho` directory 

#### 7. Script for Creating 3 Tier App via cloudformation

Clone nephos in location

    git clone https://github.com/huit/nepho.git ~/git/nepho
    export PYTHONPATH=~/git/nepho:$PYTHONPATH
  
* install dev env (hu with different args)

If you installed step 6 you do not need `./bin/nepho`

Test to see if things are working:

    ./bin/nepho -E development show-template simple-website

Validate Template 

    ./bin/nepho -E development validate-template simple-website

-----works only to here.
Deploy

    ./bin/nepho -E development deploy simple-website 

However you need to change the ssh keys in the file `nepho/deployments/simple-website.yaml` 
to reflect the name of your set of SSH keys.

To delete a deployment:

    ./bin/nepho -E development delete simple-website 

#### 8. Cloudwatch monitoring

#### 9. Script to kill stuff (hu destroy)

### General references on the arch website for AWS


TH Notes
nepho/drivers/aws/puppet-snippet.sh (puppet handoff) 
