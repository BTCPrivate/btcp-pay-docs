# Run service with systemctl



Short guide to run bitcore-node as a service. This guide will get updated once we have the service running with PM2.

#### Create bitcore-node service with systemctl

1. Copy your service file into the /etc/systemd/system folder.

```text
[Unit]
Description=Bitcore-node
After=network.target

[Service]
ExecStart=/home/ubuntu/btcp-explorer/start-service.sh
WorkingDirectory=/home/ubuntu/btcp-explorer/

[Install]
WantedBy=multi-user.target

#/home/ubuntu/btcp-explorer/node_modules/bitcore-node-btcp/bin/bitcore-node start
```

1. a Create a new start-service.sh in the /home/ubuntu/btcp-explorer/ folder

```text
#!/bin/bash
sudo /usr/local/bin/node /home/ubuntu/btcp-explorer/node_modules/bitcore-node-btcp/bin/bitcore-node start
```

1. b Give start-service.sh executable permissions.

   ```text
   chmod +x start-service.sh
   ```

2. Create system link for the .zcash-params & btcp-exploer folder the ubuntu directory to the /root directory as the script is currently outdated and looks for them in the incorrect directory

   ```text
   sudo ln -s /home/ubuntu/.zcash-params/ /root/.zcash-params/
   sudo ln -s /home/ubuntu/btcp-explorer /root/btcp-explorer
   ```

Done. You can now use the following commands:

**Start the service**

```text
sudo systemctl start bitcore-node
```

**Stop Service**

```text
sudo systemctl stop bitcore-node
```

**See the console log**

```text
journalctl -u bitcore-node
```

