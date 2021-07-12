# OpenShift ML Workshop

This workshop is focused in showing the workflow of machine learning development on OpenShift. 

It uses the content created by [@sophwats](https://github.com/sophwats), [@willb](https://github.com/willb) and [@mbogoevici](https://github.com/mbogoevici) 
and here we are building upon to create a gitops approach using the Openshift GitOps Operator.

This repo also uses the ansible-runner manifests and image that was created by [@nasx](https://github.com/nasx).

## Bootstrap

First we need to install the OpenShift GitOps Operator:

```
oc apply -k gitops/manifests/bootstrap/openshift-gitops-operator/base
```

Now we have to configure the operator, creating a project and configure some permissions:

```
oc apply -k gitops/manifests/bootstrap/openshift-gitops/base
```

To deploy the workshop content we will be using the app of apps pattern:

```
oc apply -k gitops/manifests/content/workshop/argocd/apps/bootstrap/base
```