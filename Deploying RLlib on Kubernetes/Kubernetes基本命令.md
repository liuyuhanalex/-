# Kubernetes集群的链接及验证
- <span style="color:blue">腾讯云集群链接官方说明</span> [官网链接](https://cloud.tencent.com/document/product/457/8438)

- <span style="color:blue">配置本地的链接校验证书</span>

  * kubectl config set-credentials default-admin --username=**username** --password=**password**
  * kubectl config set-cluster default-cluster --server=**server** --certificate-authority=**authortiy address**
  * kubectl config set-context default-system --cluster=default-cluster --user=default-admin
  * kubectl config use-context default-system

- <span style="color:blue">常用命令<span>

  * 查看pod信息：kubectl -n ray get pods(ray是一个namespace)
  * 进入某一个具体的pod：kubectl -n ray exec -it **pod_name** -- bash
  * 从本地拷贝文件到pod kubectl -n ray cp **local_address** **pod_name**:/**address**

- <span style="color:blue">启动ray服务</span>

  * head: ray start --head
  * worker: ray start --block --redis-address "${**RAY_HEAD_SVC**}":"${**REDIS_PORT**}" --object-manager-port "${**OBJECT_MANAGER_PORT**}" --node-manager-port "${**NODE_MANAGER_PORT**}"
