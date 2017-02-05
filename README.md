# ansible-simple-ec2
Basic ansible scripts to create a temporary ec2 instance (Debian)


Install
-------
To install 

    virtualenv .venv
    source .venv/bin/activate
    pip install -r requirements.txt


Credentials
-----------
To use AWS APIs you'll need to obtain an AWS KEY + SECRET from the AWS console.
Choose a user that has `ec2` privileges and generate and access key for them
from the `IAM` console. Place the info in the file `credentials/aws.env` using
the same format as `credentials/aws.env.template`.

Run the command:

    source credentials/aws.env

to make these credentials available in your current shell.



Gimme devserver!
----------------
To create the VPC and a devserver, run the command: 

    ansible-playbook -i inventory create.yml

You can look for the public ip of the newly created instance in `./inventory`.



I don't want it anymore
-----------------------
To delete the devserver and the VPC, run the command: 

    ansible-playbook -i inventory destroy.yml

