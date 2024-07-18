# Appendix C. Using a Reverse Proxy 

This configuration is for Ubuntu, but it should work for any Linux distribution.

1. **Installing Nginx:**
   
    Update you repository index, then install Nginx:
   
    ``` bash
      sudo apt update
    ```
    ``` bash
      sudo apt install nginx
    ```
    
    Allow access to Nginx through your firewall. if applicable:
    
    ``` bash
      sudo ufw allow 'Nginx HTTP'
    ```
    
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
    

2. **Configuring your Server Block:**
   
    Create and open a new Nginx configuration file using nano or your preferred text editor:

    ``` bash
        sudo nano /etc/nginx/sites-available/kuwaiba
    ```

    Insert the following into your new file:
   
   ``` bash
        server {
            listen 80;
            listen [::]:80;

            server_name localhost;
                
            location / {
                proxy_pass http://YOUR_IP_ADDRESS:8080;
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
3. **Run Kuwaiba and open your browser:**
   
   ``` bash
        localhost/kuwaiba
    ```
