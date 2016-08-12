## Clusterator
Docker image that can spin up or tear down clusters in GKE.

## Creating a cluster
The `create` script will iterate the list of names supplied by the [names](rootfs/names) file. It will first check to see if that name already exists in the project. If so we skip it and move on to the next name. Otherwise, we try and create a cluster with that name. Creation of the cluster is a blocking operation. After that takes place we will set the version of the cluster to the appropriate value (this operation is not blocking).

## Deleting clusters
The `delete` script will iterate all names and if that name appears in the project it will attempt to remove it (this operation is not blocking).

## Environment Variables
* `CLOUD_SDK_REPO`: Version of the cloud sdk to install. (default:`"cloud-sdk-xenial"`)
* `GCLOUD_CREDENTIALS_FILE`: Name of the exported credentials file. (default:`"clusterator.json"`)
* `GCLOUD_PROJECT_ID`: The project where clusters will be created. (default:`"deis-e2e-leasable"`)
* `NUMBER_OF_CLUSTERS`: Number of clusters to create. (default:`1`)
* `NUM_NODES`: Number of nodes to create when spinning up a new cluster. (default:`"5"`)
* `MACHINE_TYPE`: The machine size that should be used. (default:`"n1-standard-4"`)
* `ZONE`: The zone where the clusters should be placed. (default:`"us-central1-a"`)
* `VERSION`: The version of kubernetes to use. (default: the latest GKE version)
