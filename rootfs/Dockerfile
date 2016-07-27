FROM quay.io/deis/base:0.2.0

ENV CLOUD_SDK_REPO="cloud-sdk-xenial"
ENV GCLOUD_CREDENTIALS_FILE="clusterator.json"
ENV GCLOUD_PROJECT_ID="deis-e2e-leasable"
ENV NUMBER_OF_CLUSTERS=1
ENV NUM_NODES="5"
ENV MACHINE_TYPE="n1-standard-4"
ENV ZONE="us-central1-a"
ENV VERSION="1.2.5"

RUN echo "deb http://packages.cloud.google.com/apt $CLOUD_SDK_REPO main" | tee /etc/apt/sources.list.d/google-cloud-sdk.list
RUN curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
RUN apt-get update -y && apt-get install -y google-cloud-sdk

COPY . /

CMD ./create
