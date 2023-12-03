# Cloud Run And AppEngine with Cloud Deploy 

delivery pipeline sample

## Create a delivery pipeline and targets 

```
$ gcloud deploy apply --file=clouddeploy.yaml --region=asia-northeast1
```

## Archive Target Resource

```
git archive -o release-001.tar.gz HEAD
```

## Upload Target Resource

```
gsutil cp release-001.tar.gz gs://serverless-app-pipeline/release-001.tar.gz
```

## Release

```
gcloud deploy releases create release-001 --source=gs://serverless-app-pipeline/release-001.tar.gz --delivery-pipeline=serverless-app-pipeline --region=asia-northeast1  --skaffold-version=2.8 --images=hello=asia.gcr.io/pupupu-cafe/hello:latest
```
