Build process:

```
$ docker build . -t foobar
Sending build context to Docker daemon  4.096kB
Step 1/4 : FROM alpine
 ---> 196d12cf6ab1
Step 2/4 : COPY . /app
 ---> Using cache
 ---> 97eb956a253f
Step 3/4 : RUN apk add python bash
 ---> Using cache
 ---> 639d81630174
Step 4/4 : CMD python /app/app.py
 ---> Using cache
 ---> 99232f64ca49
Successfully built 99232f64ca49
Successfully tagged foobar:latest
```

Run it:

