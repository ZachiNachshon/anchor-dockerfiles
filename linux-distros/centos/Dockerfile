# OVERVIEW
# --------
# This is the Dockerfile for centos base image distribution
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
#              -t ${NAMESPACE}/centos:${TAG} \
#              .
#
# HOW TO RUN THIS CONTAINER
# -------------------------
# docker run -t -d \
#            --name=${NAMESPACE}-centos \
#            ${NAMESPACE}/centos:${TAG}
#
# HOW TO TAG THIS IMAGE
# ---------------------
# docker tag ${NAMESPACE}/centos:${TAG} \
#            ${REGISTRY}/${NAMESPACE}/centos:${TAG}
#
# HOW TO PUSH THIS IMAGE
# ----------------------
# docker push ${REGISTRY}/${NAMESPACE}/centos:${TAG}
#
FROM centos:7
LABEL maintainer="Zachi Nachshon <zachi.nachshon@gmail.com>"

CMD /bin/bash
