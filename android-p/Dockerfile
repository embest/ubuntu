FROM ubuntu:18.04
RUN apt-get update \
    && apt-get install -y openjdk-8-jdk \
    && apt-get install -y git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev libgl1-mesa-dev libxml2-utils xsltproc unzip \
    && apt-get install -y ant wget bc gawk vim python\
    && wget https://dl.google.com/android/repository/tools_r25.2.2-linux.zip \
    && mkdir -p /opt/android/ /root/.android/ \
    && unzip tools_r25.2.2-linux.zip -d /opt/android/ \
    && export PATH=/opt/android/platform-tools:/opt/android/tools:/opt/android/build-tools/27.0.1:$PATH \
    && echo y | android update sdk -u -a -t 2,9,64,55,58 \
    && echo "\nexport PATH=/opt/android/platform-tools:/opt/android/tools:/opt/android/build-tools/27.0.1:\$PATH" >> /root/.bashrc
COPY debug.keystore /root/.android/debug.keystore