FROM node:latest as base

ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
ENV ANDROID_SDK_ROOT=/opt/android-commandlinetools/bin/android-sdk
ENV PATH=$PATH:/opt/android-commandlinetools/bin/android-sdk/platform-tools:/opt/android-commandlinetools/bin/android-sdk/tools:/opt/gradle/gradle-6.8.3/bin

FROM base as linuxUpdate

RUN apt update
RUN apt upgrade -y
RUN apt install git openjdk-8-jdk wget zip -y

FROM linuxUpdate as gradleInstall

RUN wget -O gradle.zip https://services.gradle.org/distributions/gradle-6.8.3-bin.zip
RUN mkdir /opt/gradle
RUN unzip -d /opt/gradle gradle.zip
RUN rm gradle.zip

FROM gradleInstall as androidSDKInstall

RUN wget -O android-commandlinetools.zip https://dl.google.com/android/repository/commandlinetools-linux-6858069_latest.zip
RUN mkdir /opt/android-commandlinetools
RUN unzip -d /opt/android-commandlinetools android-commandlinetools.zip
RUN rm android-commandlinetools.zip
RUN mv /opt/android-commandlinetools/cmdline-tools/* /opt/android-commandlinetools
RUN rm -r /opt/android-commandlinetools/cmdline-tools
RUN mkdir /opt/android-commandlinetools/bin/android-sdk

WORKDIR /opt/android-commandlinetools/bin

RUN yes |./sdkmanager --sdk_root=android-sdk --channel=0 --install "platforms;android-29" "platform-tools" "build-tools;29.0.2"

FROM androidSDKInstall as cordovaInstall

RUN npm install -g cordova
