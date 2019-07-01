# OVERVIEW
# --------
# This is the Dockerfile for nginx
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
#              -t ${NAMESPACE}/nginx:${TAG} \
#              .
#
# HOW TO RUN THIS CONTAINER
# -------------------------
# docker run -t -d \
#            -v ${HOME}/.nginx/nginx.conf:/etc/nginx/nginx.conf:ro \
#            --name=${NAMESPACE}-nginx \
#            -p 8080:80 \
#            ${NAMESPACE}/nginx:${TAG}
#
# HOW TO TAG THIS IMAGE
# ---------------------
# docker tag ${NAMESPACE}/nginx:${TAG} \
#            ${REGISTRY}/${NAMESPACE}/nginx:${TAG}
#
# HOW TO PUSH THIS IMAGE
# ----------------------
# docker push ${REGISTRY}/${NAMESPACE}/nginx:${TAG}
#
FROM nginx:latest
LABEL maintainer="Zachi Nachshon <zachi.nachshon@gmail.com>"