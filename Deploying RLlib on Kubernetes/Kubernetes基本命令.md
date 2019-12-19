# Kubernetes集群的链接及验证
- 腾讯云集群链接官方说明![官网](https://cloud.tencent.com/document/product/457/8438)
- 配置本地的链接校验证书
  * kubectl config set-credentials default-admin --username=**username** --password=**password**
  * kubectl config set-cluster default-cluster --server=**server** --certificate-authority=**authortiy address**
  * kubectl config set-context default-system --cluster=default-cluster --user=default-admin
  * kubectl config use-context default-system
- 常用命令
  * 查看pod信息：kubectl -n ray get pods(ray是一个namespace)
  * 进入某一个具体的pod：kubectl -n ray exec -it **pod_name** -- bash
  * 从本地拷贝文件到pod kubectl -n ray cp **local_address** **pod_name**:/**address**
- 启动ray服务
  * head: ray start --head
  * worker: ray start --block --redis-address "${RAY_HEAD_SVC}":"${REDIS_PORT}" --object-manager-port "${OBJECT_MANAGER_PORT}" --node-manager-port "${NODE_MANAGER_PORT}"
