FROM fedora:35

WORKDIR /home

RUN yum install gcc-11.2.1-1.fc35 -y && \
    yum install rpm -y

RUN mkdir nasm_temp && \
    cd nasm_temp

RUN curl https://www.nasm.us/pub/nasm/releasebuilds/2.15.05/linux/nasm-2.15.05-0.fc31.x86_64.rpm -o $(pwd)/nasm.rpm

RUN rpm -ivh nasm.rpm && rm nasm.rpm -f
RUN cd ..
RUN rmdir nasm_temp