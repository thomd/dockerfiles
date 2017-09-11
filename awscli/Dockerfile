FROM alpine:latest
LABEL maintainer "Thomas Duerr <thomduerr@gmail.com>"

RUN apk --no-cache add ca-certificates groff less python py2-pip
RUN pip install awscli
RUN mkdir -p /root/.aws
RUN { \
  echo '[default]'; \
  echo 'output = json'; \
  echo 'region = $AWS_DEFAULT_REGION'; \
  echo 'aws_access_key_id = $AWS_ACCESS_KEY_ID'; \
  echo 'aws_secret_access_key = $AWS_SECRET_ACCESS_KEY'; \
} > /root/.aws/config

ENTRYPOINT [ "aws" ]
