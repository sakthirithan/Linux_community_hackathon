# Linux Community Hackathon - Linux OpenHack’26 🐧🚀

Complete documentation repository for **Linux OpenHack’26**, containing step-by-step terminal commands, network configuration details, terminal outputs, and visual screenshot evidence for all 5 hackathon tasks.

---

## 📅 Hackathon Details
- **Event:** Linux Community Hackathon - Linux OpenHack’26
- **Timing:** 9.00 AM to 11.30 AM
- **GitHub Repository:** [sakthirithan/Linux_community_hackathon](https://github.com/sakthirithan/Linux_community_hackathon.git)
- **Environment:** Ubuntu Linux (Oracle VirtualBox) / Nginx Web Server

---

## 📋 Task Overview & Status

| Task # | Task Description | Status | Documentation Link |
| :---: | :--- | :---: | :---: |
| **Task 1** | Set up an Nginx server to serve the custom HTML page provided by organizers. | ✅ Completed | [Task 1 README](./Task1/README.md) |
| **Task 2** | Access the hosted HTML page from another computer on the same network. | ✅ Completed | [Task 2 README](./Task2/README.md) |
| **Task 3** | Modify the custom HTML page from another computer and verify changes. | ✅ Completed | [Task 3 README](./Task3/README.md) |
| **Task 4** | Run a different HTML page on a separate port (8080) and verify access. | ✅ Completed | [Task 4 README](./Task4/README.md) |
| **Task 5** | Convert the hosted page into an HTTPS page and verify secure access. | ✅ Completed | [Task 5 README](./Task5/README.md) |

---

## 📂 Repository Structure

```text
.
├── README.md                                  # Main Hackathon overview & task status
├── Task1/
│   ├── README.md                              # Detailed Task 1 terminal steps & evidence
│   ├── 01_organizer_html_template.png
│   ├── 02_install_nginx.png
│   ├── 03_nginx_status_check.png
│   ├── 04_backup_default_html.png
│   ├── 05_download_custom_html.png
│   ├── 06_verify_index_html_structure.png
│   ├── 07_chmod_nginx_test_reload.png
│   ├── 08_https_port443_precheck.png
│   └── 09_final_local_http_curl_verification.png
├── Task2/
│   ├── README.md                              # Detailed Task 2 terminal steps & evidence
│   ├── 01_client_cmd_ping_and_curl.png
│   ├── 02_host_ip_and_client_ping.png
│   └── 03_remote_client_curl_headers.png
├── Task3/
│   ├── README.md                              # Detailed Task 3 terminal steps & evidence
│   ├── 01_ssh_connect_and_nano_edit.png
│   ├── 02_nginx_test_and_remote_curl.png
│   └── 03_browser_and_terminal_verification.png
├── Task4/
│   ├── README.md                              # Detailed Task 4 terminal steps & evidence
│   ├── 01_dual_port_browser_view.png
│   ├── 02_remote_client_curl_port8080.png
│   ├── 03_ssh_remote_verification_port8080.png
│   ├── 04_nginx_site_config_and_reload.png
│   └── 05_socket_listener_and_local_curl.png
└── Task5/
    ├── README.md                              # Detailed Task 5 terminal steps & evidence
    └── 01_https_ssl_curl_and_browser_verification.png
```

---

## 🔍 Detailed Task Summaries

### 🔹 [Task 1: Nginx Server Setup & Custom HTML Hosting](./Task1/README.md)
- **Summary:** Installed Nginx, downloaded organizer's custom HTML template to `/var/www/html/index.html`, set permissions (`chmod 777`), tested syntax (`nginx -t`), reloaded Nginx, and verified local HTTP serving via `curl http://localhost`.
- **Evidence:** 9 step-by-step screenshots with descriptive filenames.

### 🔹 [Task 2: LAN Accessibility Verification](./Task2/README.md)
- **Summary:** Identified Linux server IP (`10.10.144.102`), verified network connectivity via `ping`, tested HTTP header response via `curl -I http://10.10.144.102`, and confirmed browser access across the network.
- **Evidence:** 3 step-by-step screenshots with descriptive filenames.

### 🔹 [Task 3: Remote Modification via SSH](./Task3/README.md)
- **Summary:** Enabled SSH daemon on server, connected remotely via SSH, modified `/var/www/html/index.html` to add student Name (`SAKTHI M`) and Roll Number (`7376242AD284`), and verified live updates.
- **Evidence:** 3 step-by-step screenshots with descriptive filenames.

### 🔹 [Task 4: Separate Port Hosting (Port 8080)](./Task4/README.md)
- **Summary:** Created `/var/www/task4/index.html`, created Nginx virtual host listening on port `8080`, enabled symlink, verified active listening socket (`ss -lntp`), and tested dual-port browser rendering.
- **Evidence:** 5 step-by-step screenshots with descriptive filenames.

### 🔹 [Task 5: HTTPS Conversion & Secure Verification](./Task5/README.md)
- **Summary:** Generated self-signed SSL certificate with `openssl`, updated Nginx configuration to enable SSL listening on port `443`, reloaded Nginx, and verified secure access via `curl -k https://10.10.144.102` and browser HTTPS session.
- **Evidence:** 1 step-by-step screenshot with descriptive filename.

---

## 🛠️ Verification & Compliance
All implementations were performed 100% through terminal commands in strict accordance with OpenHack’26 rules. All task outputs are documented with commands and screenshot evidence.
