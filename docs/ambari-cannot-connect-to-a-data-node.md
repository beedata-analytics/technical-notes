# Ambari cannot connect to a data node

Probably OpenVPN service is down and Zookeeper cannot ping the node. To restart the service:

```bash
sudo ssh root@193.70.93.178
sudo systemctl restart openvpn@bee1.service
```
