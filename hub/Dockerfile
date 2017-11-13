FROM gcr.io/cloud-builders/gcloud

ENV PATH=$PATH:/builder/google-cloud-sdk/bin/
RUN apt-get -y update && \
    apt-get -y install wget ca-certificates && \
    wget https://github.com/kelseyhightower/hub-credential-helper/releases/download/0.0.1/hub-credential-helper-linux-amd64-0.0.1.tgz && \
    wget https://github.com/github/hub/releases/download/v2.2.8/hub-linux-amd64-2.2.8.tgz && \
    tar -xvf hub-credential-helper-linux-amd64-0.0.1.tgz && \
    tar -xvf hub-linux-amd64-2.2.8.tgz && \
    mv hub-credential-helper /usr/local/bin/hub-credential-helper && \
    mv hub-linux-amd64-2.2.8/bin/hub /usr/local/bin/hub && \

    # clean up
    apt-get -y remove wget && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf hub-linux-amd64-2.2.8.tgz && \
    rm -rf hub-credential-helper-linux-amd64-0.0.1.tgz && \
    rm -rf hub-linux-amd64-2.2.8

ENTRYPOINT ["hub"]
