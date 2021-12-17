# workdock

## 容器
#### web应用
- nginx
- php (composer, supervisor)
- mysql
- mongo
- rabbitmq
- elasticsearch
- redis
- clickhouse

#### 日志系统
- redis
- logstash
- elasticsearch
- kibana

#### 持续集成
- gitlab
- harbor
- k8s
- sonar
- walle
- docker

#### 监控系统
- grafana
- zabbix

#### 分布式
- consul
- apollo
- zookeeper


## 命令
```bash
# 构建
docker-compose build container-name

# 启动
docker-compose up container-name

# deamon启动
docker-compose up -d container-name

# 关闭
docker-compose down

# 进入容器示例
docker-compose exec container-name bash
```


