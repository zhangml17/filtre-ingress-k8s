# filtre-ingress-k8s
The whitelist mechanism for ingress access control

使用说明：

+ 修改 manifest/configmap.yaml 文件，在 white.ip.lst项下，添加外网IP（注意缩进）
+ 修改完，回到项目路径： make refresh 更新
+ 等待Haproxy pod自动重启完毕后，使用命令： kubectl -n filtre get po -o wide 对pod的工作状态进行查询
+ RESTARTS 项就是重启次数，其加1后，说明更新成功
