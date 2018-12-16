# 学习撰写docker脚本
停掉所有：

```bash
docker stop $(docker ps -q)
```

删掉所有images：

```bash
docker rmi -f $(docker images -q)
```

删掉所有containers：

```bash
docker rm -f $(docker ps -aq)
````



