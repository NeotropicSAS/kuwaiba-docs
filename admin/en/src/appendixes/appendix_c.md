# Appendix C. Using a Reverse Proxy 

Adding a reverse proxy with Nginx in front of Kuwaiba can provide several benefits:

1. Redirecting the traffic from standard HTTP/HTTPS ports 80/443 to 8080   allows  a non-privileged user to run Kuwaiba
2. Security: Nginx can help protect Kuwaiba by hiding its internal structure and adding an additional layer of security.
3. Load Balancing: If you have multiple instances of Kuwaiba, Nginx can distribute the load among them.

This configuration is for Debian, but it should work for any derivative distribution like Ubuntu.

1. Install Nginx:
   
    Update you repository index, then install Nginx:
   
    ``` bash
      sudo apt update
    ```
    ``` bash
      sudo apt install nginx
    ```

    > Note
    >
    > This step is optional, allow access to Nginx through your firewall. if applicable: 
    >
    > sudo ufw allow 'Nginx HTTP'
    > 
    
    Verify that Nginx is running:
   
   ``` bash
      systemctl status nginx
    ```

    ``` bash
      Output
        ● nginx.service - A high performance web server and a reverse proxy server
            Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)
            Active: active (running) since Mon 2022-08-29 06:52:46 UTC; 39min ago
            Docs: man:nginx(8)
        Main PID: 9919 (nginx)
            Tasks: 2 (limit: 2327)
            Memory: 2.9M
                CPU: 50ms
            CGroup: /system.slice/nginx.service
                    ├─9919 "nginx: master process /usr/sbin/nginx -g daemon on; master_process on;"
                    └─9920 "nginx: worker process   

    ```
    

2. Edit your Server Block:
   
    Create and open a new Nginx configuration file using nano or your preferred text editor:

    ``` bash
        sudo nano /etc/nginx/sites-available/kuwaiba
    ```

    Insert the following text into your new file:
   
   ``` bash
        server {
            listen 80;
            listen [::]:80;

            server_name localhost; # Replace 'localhost' with your FQDN if available
                
            location / {
                proxy_pass http://YOUR_IP_ADDRESS:PORT; # Replace PORT with the port Kuwaiba is running on (default is 8080, but could be different if the default settings were changed)
                include proxy_params;
            }
        }
    ```

   Next, enable this configuration file by creating a link from it to the sites-enabled directory that Nginx reads at startup:

    ``` bash
        sudo ln -s /etc/nginx/sites-available/kuwaiba /etc/nginx/sites-enabled/
    ```

    You can now test your configuration file for syntax errors:
    
    ``` bash
        sudo nginx -t
    ```

    With no problems reported, restart Nginx to apply your changes:
    
    ``` bash
        sudo systemctl restart nginx
    ```
3. Run Kuwaiba and open your browser:
   
   ``` bash
        localhost/kuwaiba
    ```
