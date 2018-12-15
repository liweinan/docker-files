## Django Example

- [Quickstart: Compose and Django | Docker Documentation](https://docs.docker.com/compose/django/#define-the-project-components)

### 创建项目

命令：

```bash
$ docker-compose run web django-admin.py startproject composeexample .
```

执行情况：

```bash
Starting django-compose_db_1 ... done
Building web
Step 1/7 : FROM python:3
3: Pulling from library/python
54f7e8ac135a: Pull complete
d6341e30912f: Pull complete
087a57faf949: Pull complete
5d71636fb824: Pull complete
0c1db9598990: Pull complete
bfb904e99f24: Pull complete
78a3d3a96a32: Pull complete
885a0ed92c89: Pull complete
dd7cc9ace242: Pull complete
Digest: sha256:3870d35b962a943df72d948580fc66ceaaee1c4fbd205930f32e0f0760eb1077
Status: Downloaded newer image for python:3
 ---> 1e80caffd59e
Step 2/7 : ENV PYTHONUNBUFFERED 1
 ---> Running in 4b8b6131c0cb
Removing intermediate container 4b8b6131c0cb
 ---> 0ac22bab4410
Step 3/7 : RUN mkdir /code
 ---> Running in 5641cbe5dfb7
Removing intermediate container 5641cbe5dfb7
 ---> 22e99f038f99
Step 4/7 : WORKDIR /code
 ---> Running in cfdd55cb3309
Removing intermediate container cfdd55cb3309
 ---> 25bd919b4ac9
Step 5/7 : ADD requirements.txt /code/
 ---> b92b3ef3c385
Step 6/7 : RUN pip install -r requirements.txt
 ---> Running in 72b0622b036c
Collecting psycopg2 (from -r requirements.txt (line 1))
  Downloading https://files.pythonhosted.org/packages/90/aa/b033c170c9bd505c7e4d1560f5dbb35ca2a7e928ac03c384f93d0cdaf6a7/psycopg2-2.7.6.1-cp37-cp37m-manylinux1_x86_64.whl (2.7MB)
Collecting Django<2.0,>=1.8 (from -r requirements.txt (line 2))
  Downloading https://files.pythonhosted.org/packages/09/2b/6c2d363e3d46307251a9d6bf74ec28543805bbcadf56ca729f4a04846914/Django-1.11.17-py2.py3-none-any.whl (7.0MB)
Collecting pytz (from Django<2.0,>=1.8->-r requirements.txt (line 2))
  Downloading https://files.pythonhosted.org/packages/f8/0e/2365ddc010afb3d79147f1dd544e5ee24bf4ece58ab99b16fbb465ce6dc0/pytz-2018.7-py2.py3-none-any.whl (506kB)
Installing collected packages: psycopg2, pytz, Django
Successfully installed Django-1.11.17 psycopg2-2.7.6.1 pytz-2018.7
Removing intermediate container 72b0622b036c
 ---> de2c8b7485bd
Step 7/7 : ADD . /code/
 ---> e3d913e0f9fc
Successfully built e3d913e0f9fc
Successfully tagged django-compose_web:latest
WARNING: Image for service web was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
$
```

容器的运行情况：

```bash
$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS               NAMES
dc67e22a970b        postgres            "docker-entrypoint.s…"   About an hour ago   Up About an hour    5432/tcp            django-compose_db_1
```

生成了`composeexample`和`manage.py`：

```bash
$ ls
Dockerfile         composeexample     manage.py
README.md          docker-compose.yml requirements.txt
```

`composeexample`的内容：

```bash
$ ls composeexample/
__init__.py settings.py urls.py     wsgi.py
```
