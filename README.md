# Ansible, CloudStack, user-data and google DNS Example Playbook

## What:
Example to user ansible to deploy instances and load balancer in the CloudStack, install packages and execute commands using user-data and register entry on Google DNS.

## Install by virtualenv
~~~
$ cat ~/.cloudstack.ini
[cloudstack]
endpoint = https://cloudstack.example.com/client/api
key = cloudstack api key
secret = cloudstack api secret

$ cat ~/.gcloud.json
{
  "type": "service_account",
  "project_id": "your-project-on-google-cloud",
  "private_key_id": "google cloud private key id",
  "private_key": "google cloud private key",
  "client_email": "google_client_email@your-project-on-google-cloud.iam.gserviceaccount.com",
  "client_id": "your client id",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://accounts.google.com/o/oauth2/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "https://www.googleapis.com/robot/v1/metadata/x509/google_client_email%40your-project-on-google-cloud.iam.gserviceaccount.com"
}


$ git clone https://github.com/msinhore/ansible-cloudstack-guest-example.git
$ cd ansible-cloudstack-guest-example
$ virtualenv app && source app/bin/activate
$ pip install -r requirements.txt
$ ansible-playbook playbooks/meetup.yml
~~~
