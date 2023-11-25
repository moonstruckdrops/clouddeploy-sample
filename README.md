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
