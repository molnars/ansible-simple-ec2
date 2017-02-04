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


Gimme instance
--------------


    ansible-playbook -i inventory aws/create-dev-instance.yml
