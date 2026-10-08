# Task 4: Run a Different HTML Page on a Separate Port (Port 8080)

## Objective
Configure Nginx to serve a completely separate HTML application on port `8080` alongside the primary site on port `80`, ensuring both independent web pages are accessible locally and across the network.

---

## Step-by-Step Implementation & Technical Execution

### Step 1: Create New Web Directory & HTML Page
Create a dedicated directory `/var/www/task4/` for the second site and write a custom `index.html` file.

```bash
# Create directory for Task 4 site
sudo mkdir -p /var/www/task4

# Create HTML page
sudo nano /var/www/task4/index.html
```

**Task 4 HTML Code (`/var/www/task4/index.html`):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Task 4 - Separate Port</title>
</head>
<body>
    <h1>Linux OpenHack - Task 4</h1>
    <h2>Second HTML Page</h2>
    <p>This page is running on a separate port.</p>
    <p>Port: 8080</p>
</body>
</html>
```

---

### Step 2: Configure Nginx Virtual Host for Port 8080
Create a new site block configuration file in `/etc/nginx/sites-available/task4`.

```bash
sudo nano /etc/nginx/sites-available/task4
```

**Nginx Configuration File (`/etc/nginx/sites-available/task4`):**
```nginx
server {
    listen 8080;
    listen [::]:8080;

    root /var/www/task4;
    index index.html;

    server_name _;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

---

### Step 3: Enable Site Block & Reload Nginx Service
Link the new configuration to `sites-enabled`, test Nginx syntax, and reload service.

```bash
# Symlink to sites-enabled
sudo ln -s /etc/nginx/sites-available/task4 /etc/nginx/sites-enabled/task4

# Check active symlinks
ls -l /etc/nginx/sites-enabled/

# Test syntax and reload Nginx
sudo nginx -t
sudo systemctl reload nginx
sudo systemctl status nginx
```

![Nginx Virtual Host Setup on Port 8080](./Screenshot%202026-10-08%20101041.png)

*Figure 4.1: Directory creation, Nginx site configuration link, syntax test, and service reload.*

---

### Step 4: Verify Listening Socket Status & Local Access
Confirm Nginx is actively listening on TCP port `8080` using `ss`, and test local access via `curl`.

```bash
# Verify active sockets on port 8080
sudo ss -lntp | grep ':8080'

# Test local response
curl http://localhost:8080
```

![Port 8080 Socket Status & Local Curl](./Screenshot%202026-10-08%20101057.png)

*Figure 4.2: Socket listener verification (`sudo ss -lntp`) and local `curl http://localhost:8080`.*

---

### Step 5: Remote Network Access Verification
From a remote client machine on the network, send HTTP header requests and view both sites simultaneously in the browser.

```cmd
# Remote header inspection
curl -I http://10.10.144.102:8080

# Remote body content fetch
curl http://10.10.144.102:8080
```

**Browser Verification:**
- Primary Site: `http://10.10.144.102` (Port 80) -> Serves Task 1/3 page.
- Secondary Site: `http://10.10.144.102:8080` (Port 8080) -> Serves Task 4 page.

![Dual Port Side-by-Side Browser View](./Screenshot%202026-10-08%20100838.png)

*Figure 4.3: Side-by-side browser view of Port 80 (Main) and Port 8080 (Task 4).*

![Remote Client Curl Verification](./Screenshot%202026-10-08%20101007.png)

*Figure 4.4: Fetching headers and content from remote machine via `curl -I http://10.10.144.102:8080`.*

---

## Conclusion
Task 4 has been successfully executed. A second distinct HTML application is running on port `8080` via Nginx virtual host configuration and is accessible locally and across the network.
