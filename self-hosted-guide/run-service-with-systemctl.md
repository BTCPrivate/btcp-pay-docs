# Run service with systemctl

 This is a short guide to run bitcore-node as a service. This guide will get updated once we have the service running with PM2.

#### Create bitcore-node service with systemctl

1. Copy your service file into the /etc/systemd/system folder.

{% tabs %}
{% tab title="Digital Ocean" %}


```text
[Unit]
Description=Bitcore-node
After=network.target

[Service]
ExecStart=/home/ubuntu/btcp-explorer/start-service.sh
WorkingDirectory=/home/ubuntu/btcp-explorer/

[Install]
WantedBy=multi-user.target

#/root/btcp-explorer/node_modules/bitcore-node-btcp/bin/bitcore-node start
```
{% endtab %}

{% tab title="AWS" %}


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
{% endtab %}
{% endtabs %}

1. a Create a new start-service.sh in the /home/ubuntu/btcp-explorer/ folder

{% tabs %}
{% tab title="Digital Ocean" %}


```text
#!/bin/bash
sudo /usr/local/bin/node /root/btcp-explorer/node_modules/bitcore-node-btcp/bin/bitcore-node start
```
{% endtab %}

{% tab title="AWS" %}


```text
#!/bin/bash
sudo /usr/local/bin/node /home/ubuntu/btcp-explorer/node_modules/bitcore-node-btcp/bin/bitcore-node start
```
{% endtab %}
{% endtabs %}

1. b Give start-service.sh executable permissions.

   ```text
   chmod +x start-service.sh
   ```

2. Create system link for the .zcash-params & btcp-exploer folder the ubuntu directory to the /root directory as the script is currently outdated and looks for them in the incorrect directory

{% tabs %}
{% tab title="Digital Ocean" %}


```text
sudo ln -s /root/.zcash-params/ /root/.zcash-params/
sudo ln -s /root/btcp-explorer /root/btcp-explorer
```
{% endtab %}

{% tab title="AWS" %}


```text
sudo ln -s /home/ubuntu/.zcash-params/ /root/.zcash-params/
sudo ln -s /home/ubuntu/btcp-explorer /root/btcp-explorer
```
{% endtab %}
{% endtabs %}



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

