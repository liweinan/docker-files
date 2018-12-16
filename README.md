# 学习撰写docker脚本
停掉所有：

```bash
docker stop $(docker ps -q)
```

删掉所有images：

```bash
docker rmi $(docker ps -aq)
```

删掉所有containers：

```bash
docker rmi $(docker ps -aq)
````



