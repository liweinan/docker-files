FROM alpine
ADD crash.sh /
RUN sleep 5 # sleep 5 seconds during container build(docker build .)
CMD sh /crash.sh # executed during `docker run`