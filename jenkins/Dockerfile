FROM jenkins/jenkins:2.78-alpine
LABEL maintainer "Thomas Duerr <thomduerr@gmail.com>"

# add node support
USER root
RUN apk update && apk --no-cache add nodejs

ENTRYPOINT [ "/bin/tini", "--", "/usr/local/bin/jenkins.sh" ]

