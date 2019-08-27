# OVERVIEW
# --------
# This is the Dockerfile for Jenkins master
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
#              -t ${NAMESPACE}/jenkins:${TAG} \
#              .
#
# HOW TO RUN THIS CONTAINER
# -------------------------
# docker run -t -d \
#            -v "${HOME}/.jenkins:/var/jenkins_home" \
#            -p ${JENKINS_PORT}:8080/tcp \
#            --restart always \
#            --name=${NAMESPACE}-jenkins \
#            ${NAMESPACE}/jenkins:${TAG}
#
# HOW TO TAG THIS IMAGE
# ---------------------
# docker tag ${NAMESPACE}/jenkins:${TAG} \
#            ${REGISTRY}/${NAMESPACE}/jenkins:${TAG}
#
# HOW TO PUSH THIS IMAGE
# ----------------------
# docker push ${REGISTRY}/${NAMESPACE}/jenkins:${TAG}
#
FROM jenkins/jenkins:2.189
LABEL maintainer="Zachi Nachshon <zachi.nachshon@gmail.com>"