# Zabbix Monitoring for EMQTT

# Installation

1. Place `emqtt.sh` in Zabbix external scripts folder, which typically is `/usr/lib/zabbix/externalscripts/`. See [Zabbix docs](https://www.zabbix.com/documentation/3.2/manual/config/items/itemtypes/external) if you're not sure.

    ```sh
    cd /usr/lib/zabbix/externalscripts # Or your external scripts path
    wget https://raw.githubusercontent.com/viniciusbo/zabbix-emqtt/master/externalscripts/emqtt.sh
    chmod +x emqtt.sh
    ```

1. Add the following macros to your EMQTT host in Zabbix:

    ```
    {$EMQTT_HOST} => host IP or domain
    {$EMQTT_API_USER} => admin
    {$EMQTT_API_PASS} => public
    ```
    These are the default credentials, but be sure to change it to match yours if needed.

1. Import `zbx_emqtt_template.xml` template to Zabbix and add it to your EMQTT host.

Note that there are more than 50 items monitored. I've disabled many of them but you may enable as you wish.