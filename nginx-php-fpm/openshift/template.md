# Instructions to use roopla-webapp template

Login to openshift v3 origin
```
oc login
```
Provide openshift v3 User name and password

Create a new project
```
oc new-project project-name
```

Add ssh secret for deployment.
NOTE: Sharing user private key `~/.ssh/id_rsa` is not recommended.
Instead generate a new ssh key pair, add public key to github/bitbucket/gitlab's project deployment keys and use private key here to create scmsecret.
```
oc secrets new scmsecret ssh-privatekey=~/.ssh/id_rsa -n project-name
oc secrets add serviceaccount/builder secrets/scmsecret -n project-name
```

Create Database claim
```
oc create -n project-name -f openshift/database-claim.json
```

Create Stage Application from template:
```
oc process -v APP_ENV=stage,APP_DEBUG=true -f openshift/template.json | oc create -n project-name -f -
```
We can control parameters using `-v key=value`.

Ref: https://docs.openshift.com/enterprise/3.0/dev_guide/templates.html
