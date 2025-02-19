# 🚀 Setting Up Elasticsearch on Linux 📌

---

## 🎯 Introduction
Elasticsearch is a powerful, distributed search and analytics engine used for a variety of applications, from log and security analytics to full-text search. This guide will walk you through setting up Elasticsearch on Linux step by step. 🛠️

---

## 📥 Installing Elasticsearch

### 🔹 Step 1: Download Elasticsearch ⬇️
Run the following command to download Elasticsearch (version 8.12.0, as it is the most stable version):
```bash
wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-8.12.0-linux-x86_64.tar.gz
```

### 🔹 Step 2: Extract the Archive 📂
```bash
tar -xzf elasticsearch-8.12.0-linux-x86_64.tar.gz
```

### 🔹 Step 3: Navigate to the Elasticsearch Directory 📁
```bash
cd elasticsearch-8.12.0/
```

### 🔹 Step 4: Start Elasticsearch ▶️
```bash
./bin/elasticsearch
```

### 🔹 Step 5: Verify Elasticsearch is Running ✅
After running Elasticsearch, you will receive a password. Use the following command to verify:
```bash
curl -k -u elastic:YOUR_PASSWORD https://localhost:9200
```



## 🛠 Running Elasticsearch as a Service 🚀
To ensure Elasticsearch runs as a service on Linux, follow these steps:

### 🔹 Step 1: Create a Systemd Service File 📝
```bash
sudo nano /etc/systemd/system/elasticsearch.service
```

### 🔹 Step 2: Add the Following Configuration ⚙️
Replace `/path/to/elasticsearch` with the actual installation path.
```ini
[Unit]
Description=Elasticsearch Service
After=network.target

[Service]
Type=simple
User=<your-linux-user>
Group=<your-linux-user>
ExecStart=/path/to/elasticsearch/bin/elasticsearch
Restart=always
LimitNOFILE=65536
LimitMEMLOCK=infinity

[Install]
WantedBy=multi-user.target
```
💾 **Save and exit** (CTRL+X, then Y, then ENTER).

### 🔹 Step 3: Reload Systemd and Enable the Service 🔄
```bash
sudo systemctl daemon-reload
sudo systemctl enable elasticsearch
sudo systemctl start elasticsearch
```

### 🔹 Step 4: Check Service Status 📊
```bash
sudo systemctl status elasticsearch
```
✅ **If Elasticsearch is running, you should see an active status.**

---

## 🎉 Conclusion
Congratulations! 🎊 You've successfully installed and configured Elasticsearch on Linux. Now, you can start indexing and searching your data efficiently. 🚀

🔗 **Next Steps:**
- Learn how to configure Elasticsearch for production.
- Set up Kibana for data visualization.
- Integrate with Logstash for centralized logging.

🔥 **Happy Searching!** 🔍

---

## ✨ Author
📌 **Nipun Negi**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/nipunnegi/)
