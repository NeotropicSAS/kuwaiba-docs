# Appendix B. Starting the Server on Boot

The following instructions apply to systemd-enabled distros, particularly Debian 11+. This is not a guide on how to create services in systemd, just a sample of what most production scenarios would require to run Kuwaiba on boot.

1. Create a file in ``/etc/systemd/system/`` named ``kuwaiba.service``
2. Paste the following lines inside:

    ```bash
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
    sudo systemctl daemon-reload
    ```

4. Start and enable the service

    ``` bash
    sudo systemctl start program-name
    sudo systemctl enable program-name
    ```

5. Verify the service status

    ``` bash
    sudo systemctl status program-name 
    ```

## Schedule Automatic Database Backup

The instructions below show an example of how to perform automatic backups of the Kuwaiba database. It applies to Linux distributions, specifically Debian 11.

1. Create a file named `kuwaiba_database_backup.sh`
2. Copy the following lines inside.

    ```bash
    #!/bin/bash

    # Define the paths
    NEO4J_DIR="/data/db/kuwaiba.db"
    BACKUP_DIR="/data/backups/"
    TIMESTAMP=$(date +"%Y%m%d_%H%M%S")
    BACKUP_PATH="${BACKUP_DIR}backup-${TIMESTAMP}_kuwaiba.db.tar.gz"

    # Ensure the backup directory exists
    mkdir -p "$BACKUP_DIR"

    # Create a tarball of the Neo4j data directory
    tar -czvf "$BACKUP_PATH" "$NEO4J_DIR"

    # Optional: Remove backups older than 7 days
    find "$BACKUP_DIR" -type f -name "*.tar.gz" -mtime +7 -exec rm {} \;
    ```

    This script creates a backup of the Kuwaiba database and saves it in `BACKUP_DIR`. In addition, it deletes backups that have a creation date older than 7 days.

3. Give execution permissions to the above script.

   ```bash
   chmod +x /path/to/your/bash-script.sh
   ```

4. Schedule the task in Linux. To do this, use crontab.

   ```bash
   crontab -e
   ```

   ```bash
   0 0 * * * /path/to/your/bash-script.sh
   ```
