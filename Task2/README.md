# Task 2: Access the Hosted HTML Page from Another Computer on the Same Network

## Objective
Access and verify the custom HTML page hosted on the primary Linux machine (from Task 1) from another computer connected to the same local area network (LAN), using both terminal/command prompt utilities (`ping`, `curl`) and web browser navigation.

---

## Network Architecture & System Roles

| System | Role | OS | IP Address |
| :--- | :--- | :--- | :--- |
| **Host System** | Nginx Web Server | Ubuntu Linux (Ubuntu 26.04 LTS) | `10.10.144.102` |
| **Client System** | Remote Network Client | Windows 11 (Command Prompt / Browser) | Local LAN Subnet |

---

## Step-by-Step Execution & Verification

### Step 1: Identify Host IP & Verify Nginx Service Status
On the Linux host machine running Nginx, retrieve the internal LAN IP address and confirm the web server process status.

```bash
# Obtain IP address of the host machine
hostname -I

# Verify Nginx status on host
sudo systemctl status nginx
```

**Host Results:**
- Host IP Address: `10.10.144.102`
- Nginx Service Status: `active (running)`

---

### Step 2: Test Network Reachability from Client Computer
From the client computer connected to the same network, open Command Prompt (CMD) or Terminal and execute a `ping` request to the host IP address.

```cmd
ping 10.10.144.102
```

**Ping Execution Output:**
```text
Pinging 10.10.144.102 with 32 bytes of data:
Reply from 10.10.144.102: bytes=32 time<1ms TTL=64
Reply from 10.10.144.102: bytes=32 time<1ms TTL=64
Reply from 10.10.144.102: bytes=32 time<1ms TTL=64
Reply from 10.10.144.102: bytes=32 time<1ms TTL=64

Ping statistics for 10.10.144.102:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 1ms, Average = 0ms
```

![Ping Verification from Remote Client](./Screenshot%202026-10-08%20094651.png)

*Figure 2.1: Terminal ping verification and active Nginx status on host `10.10.144.102`.*

---

### Step 3: Test Remote HTTP Request and Headers via `curl`
From the client computer, send an HTTP head and full request to the Nginx web server on `10.10.144.102`.

```cmd
# Inspect HTTP Response Headers from remote computer
curl -I http://10.10.144.102
```

**Response Output:**
```text
HTTP/1.1 200 OK
Server: nginx/1.28.3 (Ubuntu)
Date: Thu, 08 Oct 2026 04:15:36 GMT
Content-Type: text/html
Content-Length: 382
Last-Modified: Thu, 08 Oct 2026 03:47:57 GMT
Connection: keep-alive
ETag: "6ac7126d-17e"
Accept-Ranges: bytes
```

![Remote Curl HTTP Response Verification](./Screenshot%202026-10-08%20094659.png)

*Figure 2.2: Fetching headers and HTML content from remote client via `curl -I http://10.10.144.102`.*

---

### Step 4: Web Browser Remote Access
Open a web browser on the client machine and enter the IP address of the host machine:

```url
http://10.10.144.102
```

**Result:** The browser successfully renders the hosted "Linux Community - OpenHack Hackathon" custom HTML page across the local network.

---

## Conclusion
Task 2 has been successfully completed. The custom HTML page hosted on the Nginx web server is fully accessible across the local network from secondary computers via terminal tools (`ping`, `curl`) and web browsers.
