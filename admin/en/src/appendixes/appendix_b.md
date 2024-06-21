# Appendix B. Starting the Server on Boot
The following instructions apply to systemd-enabled distros, particularly Debian 11+. This is not a guide on how to create services in systemd, just a sample of what most production scenarios would require to run Kuwaiba on boot.
1. Create a file in ``/etc/systemd/system/`` named ``kuwaiba.service``
2. Paste the following lines inside:

``` 
[Unit]
Description= Kuwaiba Open Network Inventory
After=network.target

[Service]
User=kuwaiba
ExecStart=nohup /usr/bin/java -jar /path/file/kuwaiba_server_2.1.x-stable.jar
SuccessExitStatus=143
TimeoutStopSec=10
Restart=on-failure
RestartSec=5

[Install]
WantedBy=multi-user.target
```

> **Note**
>
> Make sure that the `User` field is set to the user that will be used to run the server. Also, double-check the `ExecStart` command syntax before saving. 

3. Reload the service definitions
   
``` bash
$ sudo systemctl daemon-reload
```

4. Start and enable the service

``` bash
$ sudo systemctl start program-name
$ sudo systemctl enable program-name
```

5. Verify the service status

``` bash
$ sudo systemctl status program-name 
```