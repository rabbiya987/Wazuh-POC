
---

# 🛡️ File Integrity Monitoring (FIM) with Wazuh

**File Integrity Monitoring (FIM)** helps in auditing sensitive files and meeting regulatory compliance requirements. Wazuh has a built-in FIM module that monitors file system changes to detect **creation, modification, and deletion** of files.

In this guide, we will test the Wazuh FIM module by monitoring a directory on a Kali Linux endpoint.

---

## ⚙️ Configuration on the Kali Linux Endpoint

1. **Edit the Wazuh Agent Configuration**

   Open the Wazuh agent configuration file:

   ```bash
   sudo nano /var/ossec/etc/ossec.conf
   ```

2. **Add a Directory for Monitoring**
   Inside the `<syscheck>` block, add:

   ```xml
   <directories check_all="yes" report_changes="yes" realtime="yes">/root</directories>
   ```

3. **Restart the Wazuh Agent**
   Apply the configuration changes:

   ```bash
   sudo systemctl restart wazuh-agent
   ```

---

## 🧪 Testing the Configuration

Perform the following steps in the monitored `/root` directory:

1. **Create a text file**

   ```bash
   sudo touch /root/testfile.txt
   ```

   Wait **5 seconds**.

2. **Modify the file**

   ```bash
   echo "This is a test" | sudo tee -a /root/testfile.txt
   ```

   Wait **5 seconds**.

3. **Delete the file**

   ```bash
   sudo rm /root/testfile.txt
   ```

---

## 📊 Viewing Alerts in the Wazuh Dashboard

1. Navigate to the **Threat Hunting** module.
2. Apply the filter:

   ```
   rule.id:550
   ```
3. You should see alerts for **file creation, modification, and deletion**.

---

![FIM Alert Example](assets/Figure2.png)

---

