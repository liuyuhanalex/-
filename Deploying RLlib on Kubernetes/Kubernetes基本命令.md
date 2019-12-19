# Kubernetes集群的链接及验证
- 腾讯云集群链接官方说明[官网](https://cloud.tencent.com/document/product/457/8438)
- 配置本地的链接校验证书
  * kubectl config set-credentials default-admin --username=<username> --password=<password>
  * kubectl config set-cluster default-cluster --server=<server> --certificate-authority=<authortiy address>
  * kubectl config set-context default-system --cluster=default-cluster --user=default-admin
  * kubectl config use-context default-system
- 常用命令
  * 查看pod信息：kubectl -n ray get pods(ray是一个namespace)
  * 
