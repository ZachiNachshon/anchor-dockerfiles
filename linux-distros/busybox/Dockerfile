# OVERVIEW
# --------
# This is the Dockerfile for busybox
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
#              -t ${NAMESPACE}/busybox:${TAG} \
#              .
#
# HOW TO RUN THIS CONTAINER
# -------------------------
# docker run -t -d \
#            --name=${NAMESPACE}-busybox \
#            -p 8080:80 \
#            ${NAMESPACE}/busybox:${TAG}
#
# HOW TO TAG THIS IMAGE
# ---------------------
# docker tag ${NAMESPACE}/busybox:${TAG} \
#            ${REGISTRY}/${NAMESPACE}/busybox:${TAG}
#
# HOW TO PUSH THIS IMAGE
# ----------------------
# docker push ${REGISTRY}/${NAMESPACE}/busybox:${TAG}
#
FROM busybox:latest
LABEL maintainer="Zachi Nachshon <zachi.nachshon@gmail.com>"