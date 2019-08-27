# OVERVIEW
# --------
# This is the Dockerfile for alpine base image distribution
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
#              -t ${NAMESPACE}/alpine:${TAG} \
#              .
#
# HOW TO RUN THIS CONTAINER
# -------------------------
# docker run -t -d \
#            --name=${NAMESPACE}-alpine \
#            ${NAMESPACE}/alpine:${TAG}
#
# HOW TO TAG THIS IMAGE
# ---------------------
# docker tag ${NAMESPACE}/alpine:${TAG} \
#            ${REGISTRY}/${NAMESPACE}/alpine:${TAG}
#
# HOW TO PUSH THIS IMAGE
# ----------------------
# docker push ${REGISTRY}/${NAMESPACE}/alpine:${TAG}
#
FROM alpine:latest
LABEL maintainer="Zachi Nachshon <zachi.nachshon@gmail.com>"

CMD /bin/sh