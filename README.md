# Cloud Run with Cloud Deploy 

build

```
$skaffold build
Generating tags...
 - asia.gcr.io/pupupu-cafe/hello -> asia.gcr.io/pupupu-cafe/hello:5fffebd-dirty
Checking cache...
 - asia.gcr.io/pupupu-cafe/hello: Found Remotely
```

deploy

```
$ skaffold deploy -p staging-app --images asia.gcr.io/pupupu-cafe/hello:latest
Tags used in deployment:
 - asia.gcr.io/pupupu-cafe/hello -> asia.gcr.io/pupupu-cafe/hello:latest
Starting deploy...
Starting pre-deploy hooks...
pre-deploy host hook running on macmini.local!
Completed pre-deploy hooks
Deploying Cloud Run service:
	 hello
hello: Service starting: Deploying Revision. Waiting on revision hello-00003-llm.
Cloud Run Service hello finished: Service started. 0/1 deployment(s) still pending
Starting post-deploy hooks...
post-deploy host hook running on macmini.local!
Completed post-deploy hooks
```

setup service account role

```
$skaffold deploy -p production-app --images asia.gcr.io/pupupu-cafe/hello:latest
Tags used in deployment:
 - asia.gcr.io/pupupu-cafe/hello -> asia.gcr.io/pupupu-cafe/hello:latest
Starting deploy...
Starting pre-deploy hooks...
pre-deploy host hook running on macmini.local!
Completed pre-deploy hooks
Deploying Cloud Run service:
	 hello
Cloud Run Service hello failed with error: Service failed to start: Revision 'hello-00003-r27' is not ready and cannot serve traffic. Google Cloud Run Service Agent service-1083882956739@serverless-robot-prod.iam.gserviceaccount.com must have permission to read the image, asia.gcr.io/pupupu-cafe/hello:latest. Ensure that the provided container image URL is correct and that the above account has permission to access the image. If you just enabled the Cloud Run API, the permissions might take a few minutes to propagate. Note that the image is from project [pupupu-cafe], which is not the same as this project [moonstruckdrops]. Permission must be granted to the Google Cloud Run Service Agent service-1083882956739@serverless-robot-prod.iam.gserviceaccount.com from this project.
skaffold deployment failed. 0/1 failed to complete
```

set Storage Object User Role
(roles/storage.objectUser)

```
$skaffold deploy -p production-app --images asia.gcr.io/pupupu-cafe/hello:latest
Tags used in deployment:
 - asia.gcr.io/pupupu-cafe/hello -> asia.gcr.io/pupupu-cafe/hello:latest
Starting deploy...
Starting pre-deploy hooks...
pre-deploy host hook running on macmini.local!
Completed pre-deploy hooks
Deploying Cloud Run service:
	 hello
hello: Service starting: Deploying Revision. Waiting on revision hello-00006-jcj.
hello: Service starting: Assigning traffic to latest specified targets.
hello: Service starting: Assigning traffic to latest specified targets.
Cloud Run Service hello finished: Service started. 0/1 deployment(s) still pending
Starting post-deploy hooks...
post-deploy host hook running on macmini.local!
Completed post-deploy hooks
```
