FROM ubuntu:16.04
RUN apt-get update && apt-get install -y software-properties-common sudo 
RUN add-apt-repository ppa:longsleep/golang-backports && apt-get update
RUN apt-get install -y git golang-go=2:1.13~1longsleep1+xenial iptables ipset iproute2 ebtables
RUN go get -v -t -d ./... 
RUN if [ -f Gopkg.toml ]; then curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh ; fi 
RUN go get github.com/docker/libnetwork/driverapi
RUN go get github.com/gorilla/mux
RUN go get github.com/jstemmer/go-junit-report
RUN go get github.com/axw/gocov/gocov
RUN go get github.com/AlekSi/gocov-xml
RUN go get -u gopkg.in/matm/v1/gocov-html
