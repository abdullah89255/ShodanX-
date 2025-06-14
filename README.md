# ShodanX-
Here are more practical examples of using **ShodanX** to explore its features further.

---

### **1. Basic Host and IP Information**

* **Get detailed information about an IP address:**

  ```bash
  shodanx host --ip 1.1.1.1
  ```

  *Output includes:*

  * Open ports
  * Running services
  * Hostname and location
  * Associated vulnerabilities

* **Check all hosts in a given range (CIDR):**

  ```bash
  shodanx host --cidr 192.168.1.0/24
  ```

---

### **2. Advanced Search Queries**

* **Search for devices by specific port:**

  ```bash
  shodanx search --query "port:22"
  ```

  *Find all devices running SSH (port 22).*

* **Search for vulnerable devices:**

  ```bash
  shodanx search --query "vuln:CVE-2022-1388"
  ```

* **Filter devices based on organization:**

  ```bash
  shodanx org --name "Microsoft"
  ```

---

### **3. Domain and Subdomain Searches**

* **Find all subdomains of a domain:**

  ```bash
  shodanx subdomain --name example.com
  ```

* **Get DNS records for a domain:**

  ```bash
  shodanx domain --name example.com
  ```

---

### **4. SSL and Certificates**

* **Get SSL details for a website:**

  ```bash
  shodanx ssl --host example.com
  ```

  *Includes details about the certificate, expiry date, and vulnerabilities.*

* **Find devices with expired SSL certificates:**

  ```bash
  shodanx search --query "ssl.cert.expired:true"
  ```

---

### **5. Exploit and Vulnerability Searches**

* **Find devices vulnerable to specific exploits:**

  ```bash
  shodanx search --query "apache vulnerability:CVE-2021-41773"
  ```

* **Get CVE details for a specific IP:**

  ```bash
  shodanx cvedb --ip 8.8.8.8
  ```

---

### **6. Exporting and Mapping Results**

* **Export search results to a JSON file:**

  ```bash
  shodanx search --query "nginx" --output results.json
  ```

* **Create a map of all results:**

  ```bash
  shodanx map --query "nginx" --output map.html
  ```

  *Opens an interactive map showing device locations.*

---

### **7. ShodanX Modules**

#### **Custom Search**

* Build a query using specific parameters:

  ```bash
  shodanx custom --query "org:'Google' port:443 country:US"
  ```

#### **EntityDB**

* Fetch stored entities (hosts, domains, etc.):

  ```bash
  shodanx entitydb --list
  ```

#### **Exposure Database**

* Search for exposed sensitive data:

  ```bash
  shodanx exposuredb --query "camera"
  ```

#### **Favicon Mapping**

* Search using favicon hash:

  ```bash
  shodanx faviconmap --hash <HASH_VALUE>
  ```

---

### **8. Real-World Applications**

#### **Finding Open Cameras:**

```bash
shodanx search --query "webcamxp port:8080"
```

#### **Identify Misconfigured Routers:**

```bash
shodanx search --query "port:23 product:router"
```

#### **Discover Publicly Exposed Databases:**

```bash
shodanx search --query "port:27017"
```

#### **Detect ICS/SCADA Systems:**

```bash
shodanx search --query "tag:ics"
```

#### **Search for IoT Devices by Manufacturer:**

```bash
shodanx search --query "netgear port:80"
```

---

### **Need Help With Advanced Scenarios?**

If you need help building complex queries or integrating ShodanX into a script, let me know!
