# Linux Community Hackathon - Linux OpenHack’26 🐧🚀

Complete documentation repository for **Linux OpenHack’26**, containing step-by-step terminal commands, network configuration details, terminal outputs, and visual evidence for each hackathon task.

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
| **Task 5** | Convert the hosted page into an HTTPS page and verify secure access. | ⏳ Pending | Task 5 Guide |

---

## 📂 Repository Structure

```text
.
├── README.md                      # Main Hackathon overview & task status
├── Task1/
│   ├── README.md                  # Detailed Task 1 terminal steps & evidence
│   ├── Screenshot 2026-10-08 090416.png
│   ├── Screenshot 2026-10-08 092329.png
│   ├── Screenshot 2026-10-08 092340.png
│   ├── Screenshot 2026-10-08 092350.png
│   ├── Screenshot 2026-10-08 092359.png
│   ├── Screenshot 2026-10-08 092410.png
│   ├── Screenshot 2026-10-08 092420.png
│   ├── Screenshot 2026-10-08 092427.png
│   └── Screenshot 2026-10-08 092438.png
├── Task2/
│   ├── README.md                  # Detailed Task 2 terminal steps & evidence
│   ├── Screenshot 2026-10-08 094651.png
│   └── Screenshot 2026-10-08 094659.png
├── Task3/
│   ├── README.md                  # Detailed Task 3 terminal steps & evidence
│   ├── Screenshot 2026-10-08 095751.png
│   ├── Screenshot 2026-10-08 095910.png
│   └── Screenshot 2026-10-08 100021.png
└── Task4/
    ├── README.md                  # Detailed Task 4 terminal steps & evidence
    ├── Screenshot 2026-10-08 100838.png
    ├── Screenshot 2026-10-08 101007.png
    ├── Screenshot 2026-10-08 101024.png
    ├── Screenshot 2026-10-08 101041.png
    └── Screenshot 2026-10-08 101057.png
```

---

## 🔍 Detailed Task Summaries

### 🔹 [Task 1: Nginx Server Setup & Custom HTML Hosting](./Task1/README.md)
- **Summary:** Installed Nginx, downloaded the custom HTML page from the organizer's link into `/var/www/html/index.html`, set up file permissions (`chmod 777`), tested syntax (`nginx -t`), reloaded Nginx, and verified local serving via `curl http://localhost`.
- **Evidence:** 9 step-by-step screenshots.

### 🔹 [Task 2: LAN Accessibility Verification](./Task2/README.md)
- **Summary:** Identified Linux server IP (`10.10.144.102`), verified cross-machine ping response from remote Windows client, tested HTTP header response via `curl -I http://10.10.144.102`, and confirmed browser access across the network.
- **Evidence:** 2 step-by-step screenshots.

### 🔹 [Task 3: Remote Modification via SSH](./Task3/README.md)
- **Summary:** Enabled SSH daemon on the server, established SSH session from client computer, edited `/var/www/html/index.html` to add student Name and Roll Number, and verified real-time webpage updates via `curl` and web browser.
- **Evidence:** 3 step-by-step screenshots.

### 🔹 [Task 4: Separate Port Hosting (Port 8080)](./Task4/README.md)
- **Summary:** Created `/var/www/task4/index.html`, created an Nginx site configuration in `/etc/nginx/sites-available/task4` listening on port `8080`, enabled symlink, reloaded Nginx, verified socket via `ss -lntp`, and tested dual-port browser rendering.
- **Evidence:** 5 step-by-step screenshots.

---

## 🛠️ Verification & Compliance
All implementations were performed 100% through terminal commands in strict accordance with OpenHack’26 rules. All task outputs are documented with commands and screenshot evidence.
