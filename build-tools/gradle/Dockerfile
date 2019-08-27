# OVERVIEW
# --------
# This is a base Dockerfile for Gradle
#
# REQUIRED BASE IMAGE TO BUILD THIS IMAGE
# ---------------------------------------
# This Dockerfile requires the base image anchor/java8-base
#
# REQUIRED FILES TO BUILD THIS IMAGE
# ----------------------------------
# (1) None.
#
# HOW TO BUILD THIS IMAGE
# -----------------------
# docker build -f Dockerfile \
#              --build-arg GRADLE_VERSION=${TAG} \
#              -t ${NAMESPACE}/gradle:${TAG} \
#              .
#
# HOW TO RUN THIS CONTAINER
# -------------------------
# None.
#
# HOW TO TAG THIS IMAGE
# ---------------------
# None.
#
# HOW TO PUSH THIS IMAGE
# ----------------------
# None.
#
FROM anchor/java8-base:latest
LABEL maintainer="Zachi Nachshon <zachi.nachshon@gmail.com>"

RUN apk add --no-cache curl tar bash procps

# Downloading and installing Gradle
# 1. Define a constant with the version of gradle you want to install
ARG GRADLE_VERSION

# 2. Define the URL where gradle can be downloaded from
ARG GRADLE_BASE_URL=https://services.gradle.org/distributions

# 3. Create the directories, download gradle, validate the download, install it, remove downloaded file and set links
RUN mkdir -p /usr/share/gradle /usr/share/gradle/ref \
  && echo "Downloading Gradle ${GRADLE_VERSION} binary..." \
  && curl -fsSL -o /tmp/gradle.zip ${GRADLE_BASE_URL}/gradle-${GRADLE_VERSION}-bin.zip \
  \
  && echo "Unziping Gradle..." \
  && unzip -d /usr/share/gradle /tmp/gradle.zip \
   \
  && echo "Cleaning and setting links..." \
  && rm -f /tmp/gradle.zip \
  && ln -s /usr/share/gradle/gradle-${GRADLE_VERSION} /usr/bin/gradle

# 4. Define environment variables required by gradle
ENV GRADLE_VERSION ${GRADLE_VERSION}
ENV GRADLE_HOME /usr/bin/gradle
ENV GRADLE_USER_HOME /cache

ENV PATH $PATH:$GRADLE_HOME/bin

VOLUME $GRADLE_USER_HOME

CMD [""]
