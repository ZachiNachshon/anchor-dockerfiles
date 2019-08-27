# OVERVIEW
# --------
# This is the Dockerfile for Java 8
#
# REQUIRED BASE IMAGE TO BUILD THIS IMAGE
# ---------------------------------------
# None.
#
# REQUIRED FILES TO BUILD THIS IMAGE
# ----------------------------------
# (1) None.
#
# HOW TO BUILD THIS IMAGE
# -----------------------
# docker build -f Dockerfile \
#              -t anchor/java8-base \
#              .
#
# HOW TO RUN THIS CONTAINER
# -------------------------
# None.
#
# HOW TO TAG THIS IMAGE
# ---------------------
# docker tag anchor/java8-base \
#            ${REGISTRY}/anchor/java8-base
#
# HOW TO PUSH THIS IMAGE
# ----------------------
# docker push ${REGISTRY}/anchor/java8-base
#
FROM anapsix/alpine-java:8u202b08_jdk

LABEL maintainer="Zachi Nachshon <zachi.nachshon@gmail.com>"

#-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
#          ENVIRONMENT
#-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

RUN apk update && apk add \
 wget \
 curl \
 vim \
 unzip \
 zip \
 busybox-extras \
 lsof \
 bash-completion

RUN alias l="ls -lah"