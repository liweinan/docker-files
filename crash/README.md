```bash
$ docker build . -t crash
Sending build context to Docker daemon  3.072kB
Step 1/3 : FROM alpine
 ---> 196d12cf6ab1
Step 2/3 : ADD crash.sh /
 ---> 05117d5688af
Step 3/3 : CMD sh /crash.sh
 ---> Running in b0cde246880f
Removing intermediate container b0cde246880f
 ---> 9ef2f32e2c6a
Successfully built 9ef2f32e2c6a
Successfully tagged crash:latest
```

```bash
$ docker run crash
Start to sleep 10 seconds...
done!
```