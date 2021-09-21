# [Choice] Python version: 3, 3.8, 3.7, 3.6
ARG PYTHON_VARIANT=3.9
FROM python:${PYTHON_VARIANT}

# Install python dependencies
COPY requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir \
   install -r /tmp/pip-tmp/requirements.txt && rm -rf /tmp/pip-tmp

# Install OpenJDK
ARG OPENJDK_VARIANT=11
RUN apt-get update && \
    apt-get install -y openjdk-${OPENJDK_VARIANT}-jre-headless && \
    apt-get clean;