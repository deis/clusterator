FROM quay.io/deis/base:v0.3.5

ENV CLOUD_SDK_REPO="cloud-sdk-xenial" \
	GCLOUD_CREDENTIALS_FILE="clusterator.json" \
	GCLOUD_PROJECT_ID="deis-e2e-leasable" \
	NUMBER_OF_CLUSTERS=1 \
	NUM_NODES="5" \
	MACHINE_TYPE="n1-standard-4" \
	ZONE="us-central1-a"

RUN echo "deb http://packages.cloud.google.com/apt $CLOUD_SDK_REPO main" | tee /etc/apt/sources.list.d/google-cloud-sdk.list && \
	curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add - && \
	apt-get update -y && apt-get install -y google-cloud-sdk

COPY . /

CMD ./create
