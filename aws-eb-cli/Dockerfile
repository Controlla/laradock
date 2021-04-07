FROM python:slim

LABEL maintainer="melchabcede@gmail.com"

RUN pip install --upgrade --no-cache-dir awsebcli
RUN pip install awscli --upgrade
RUN apt-get -yqq update && apt-get -yqq install git-all

#NOTE: make sure ssh keys are added to ssh_keys folder

RUN mkdir root/tmp_ssh
COPY /ssh_keys/. /root/.ssh/
RUN cd /root/.ssh && chmod 600 * && chmod 644 *.pub

COPY /profiles/. /root/.aws/
RUN cd /root/.aws && chmod 600 *

# Set default work directory
WORKDIR /var/www


