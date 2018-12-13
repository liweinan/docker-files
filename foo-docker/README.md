Build process:

```
$ docker build . -t foobar
Sending build context to Docker daemon  3.072kB
Step 1/4 : FROM alpine
 ---> 196d12cf6ab1
Step 2/4 : COPY . /app
 ---> Using cache
 ---> 40db850aa2e4
Step 3/4 : RUN apk add python
 ---> Using cache
 ---> 7a49f52233e6
Step 4/4 : CMD python /app/app.py
 ---> Using cache
 ---> 2cc11f3fb6c3
Successfully built 2cc11f3fb6c3
Successfully tagged foobar:latest
```