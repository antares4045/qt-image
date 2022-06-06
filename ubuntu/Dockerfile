FROM ubuntu:22.10

RUN apt-get update -y
RUN apt-get install git -y
RUN apt-get install wget -y

RUN apt-get install gcc -y
RUN apt-get install make -y
RUN apt-get install gdb -y
RUN apt-get install "^libxcb.*" -y
RUN apt-get install libx11-xcb-dev -y

RUN apt-get install g++ -y

RUN apt-get install odbcinst1debian2 libodbc1 odbcinst unixodbc -y
RUN apt-get install odbc-postgresql -y 
# возможно, нужен dev

RUN apt install python2-minimal -y
RUN apt-get install perl -y



#война за qt
WORKDIR /core_sources/core_sources/5.12.12/Src/
RUN ./configure -prefix $PWD/qtbase -commercial -release -nomake tests -nomake examples -confirm-license
# дрюня сказал сделать -debug, но я редиска
RUN make -j 4