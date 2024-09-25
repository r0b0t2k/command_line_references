#This command will create a pod/container with an image and whatever default command you pass it.
` kubectl run web-server --image registry.access.redhat.com/ubi8/httpd-24 --command -- cmd arg1 arg2 .... `

# To make it an interactive session do the following.
oc run -it web-server --image registry.access.redhat.com/ubi9/ubi

# Restart policy for failed containers can be Never, OnFailure, Always, default is always if omitted.
oc run -it my-app --image registry.access.redhat.com/ubi9/ubi --restart Never --command -- date

# Add --rm to delete the pod after it completes, probably needs to be used wth --retart Never
oc run -it my-app --rm --image registry.access.redhat.com/ubi9/ubi --restart Never --command -- date

# To add environment variables you can add --env= ENVIRONMENT_VAR=myvalue
oc run -it my-app --image registry.access.redhat.com/ubi9/ubi --restart Never --env= ENVIRONMENT_VAR=myvalue --command -- date
