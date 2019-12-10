## Running

Execute the following command to run this docker directly:

`$ docker run -it -p 9090:9090 -p 1883:1883 -p 5683:5683/udp -v ~/.mytb-data:/data -v ~/.mytb-logs:/var/log/thingsboard --name mytb --restart always thingsboard/tb-cassandra`

Where:

- `docker run` - run this container
- `-it` - attach a terminal session with current ThingsBoard process output
- `-p 9090:9090` - connect local port 9090 to exposed internal HTTP port 9090
- `-p 1883:1883` - connect local port 1883 to exposed internal MQTT port 1883
- `-p 5683:5683` - connect local port 5683 to exposed internal COAP port 5683
- `-v ~/.mytb-data:/data` - mounts the host's dir `~/.mytb-data` to ThingsBoard DataBase data directory
- `-v ~/.mytb-logs:/var/log/thingsboard` - mounts the host's dir `~/.mytb-logs` to ThingsBoard logs directory
- `--name mytb` - friendly local name of this machine
- `--restart always` - automatically start ThingsBoard in case of system reboot and restart in case of failure.
- `thingsboard/tb-cassandra` - docker image

After executing this command you can open http://{yor-host-ip}:9090 in you browser. You should see ThingsBoard login page. Use the following default credentials:

- **Systen Administrator**: * [sysadmin@thingsboard.org](mailto:sysadmin@thingsboard.org) / sysadmin
- **Tenant Administrator**: * [tenant@thingsboard.org](mailto:enant@thingsboard.org) / tenant
- **Customer User**: * [customer@thingsboard.org](mailto:customer@thingsboard.org) / customer

You can always change passwords for each account in account profile page.