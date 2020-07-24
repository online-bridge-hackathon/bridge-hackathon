
# DevOps

## Overview

We deploy software to GCP (Google Cloud Platform) and run cloud infrastructure there to enable availabl online services

## GCP

URL = https://console.cloud.google.com/home/dashboard?project=online-bridge-hackathon-2020
 
## IAM roles
https://cloud.google.com/iam/docs/understanding-custom-roles

## Least Privilege
https://cloud.google.com/iam/docs/using-iam-securely#least_privilege

## Security guide
https://www.fourcast.io/blog/security-guide-rbac-on-google-kubernetes-engine

## Role management

Generally custom roles are defined in yaml files and user account emails are stored in a file to be used in batch scripting, until G Suite Groups are available.

### create custom role
`gcloud iam roles create BridgeHackathonDevelopers --project=online-bridge-hackathon-2020 --file=devops/gcp-role-developer.yaml`

### describe a particular role 
```
gcloud iam roles describe --project=online-bridge-hackathon-2020 BridgeHackathonDevelopers
description: Custom role based on least privilege to be able to develop on GCP
etag: BwWp9tPDv5c=
includedPermissions:
- billing.resourceCosts.get
- container.apiServices.get
- container.apiServices.list
- container.clusters.get
- container.clusters.getCredentials
- resourcemanager.projects.get
name: projects/online-bridge-hackathon-2020/roles/BridgeHackathonDevelopers
stage: GA
title: 'Bridge Hackathon : Developers'
```

### add knaves (Tech Leads) to roles
#### custom roles
knaves is a text file with one knave email address per line
```
for user in $(cat knaves) ; do gcloud projects add-iam-policy-binding online-bridge-hackathon-2020 --member=user:${user} --role=projects/online-bridge-hackathon-2020/roles/BridgeHackathonDevelopers ; done
```

#### predefined roles
```
for role in compute.admin compute.loadBalancerAdmin ; do for user in $(cat knaves) ; do gcloud projects add-iam-policy-binding online-bridge-hackathon-2020 --member=user:${user} --role=roles/${role} ; done; done
```
