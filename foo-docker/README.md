Build process:

```bash
$ docker build . -t foobar
Sending build context to Docker daemon  4.096kB
Step 1/4 : FROM alpine
 ---> 196d12cf6ab1
Step 2/4 : COPY . /app
 ---> 3bcdc4a4f6cf
Step 3/4 : RUN apk add python bash
 ---> Running in 7625c6e4f5f2
...
Executing busybox-1.28.4-r1.trigger
OK: 52 MiB in 24 packages
Removing intermediate container 7625c6e4f5f2
 ---> 3795ddb00f0c
Step 4/4 : CMD python /app/app.py > app.out
 ---> Running in 59c815fcde42
Removing intermediate container 59c815fcde42
 ---> 2029333d02cb
Successfully built 2029333d02cb
Successfully tagged foobar:latest
```

下面的运行方式不会出发`RUN`：

```bash
$ docker run -it foobar bash
bash-4.4# exit
exit
```

下面的运行方式会触发`RUN`：

```bash
$ docker run -i foobar
Hello, world!
```

上面的命令生成了两个containers：

```bash
$ docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                     PORTS               NAMES
8b5d1e19475d        foobar              "/bin/sh -c 'python …"   4 seconds ago       Exited (0) 3 seconds ago                       youthful_neumann
9504ba1ad758        foobar              "bash"                   11 seconds ago      Exited (0) 8 seconds ago                       frosty_lamarr
```

删掉所有containers：

```bash
$ docker rm $(docker ps -a -q)
8b5d1e19475d
9504ba1ad758
```

删掉所有的images：

```bash
$ docker rmi $(docker images -q)
```





