# IDS, Firewalls and Honeypots

## <u>IDS/IPS - Basic Concepts</u>

**Intrusion Prevention System (IPS)** - ACTIVE monitoring of activity looking for anomalies and alerting/notifiying AND **taking action when they are found**.

**Intrusion Detection System (IDS)** - PASSIVE monitoring of activity looking for anomalies and alerting/notifying when they are found.

<p align="center">
<img width="100%" src="https://cdn.ttgtmedia.com/rms/onlineImages/security-ids_vs_ips-f.png" />
</p>

### **Deployment Types - HIDS & NIDS & WIDS:**
1. **Host based** - Monitors activity on a single device/host by being installed lcoally.

2. **Network based** - Monitors activity across a network using remote sensors that reprot back to a central system. Often paired with a security Information & SIEM system for analysis. Often Reverse ARP or Reverse DNS lookups are used to discover the source

### **Knowledge & Behavior-Based Detection:**
1. **Knowledge Based (Signature Based | Pattern Matching)** - Most common form of detection. Uses a database of profiles, or signatures to assess all traffic against.

2. **Behavior Based (Statistical | Anomaly | Heuristic)** - Starts by creating a baseline of behavior for the monitored system/network and then comapres all traffic against that looking for deviations. Can be labeled an AI or Expert system.

---
### **Types of IDS Alerts**
- **True Positive** --> Attack - Alert ✅✅
- **False Positive** --> No Attack - Alert ❌✅
- **False Negative** --> Attack - No Alert ✅❌
  - *This is the worst scenario*
- **True Negative** --> No Attack - No Alert ❌❌

---

## <u>Firewalls - Basic Concepts</u>
*device that monitors and filters incoming and outgoing network traffic based on an organization's previously established security policies*

### **Firewalls types:**
- **Stateful (Dynamic Packet Filtering)** - Layer 3 + 4 (Network + Transport layer)
- **Stateless (Static Packet Filtering)** - Layer 3 (Network)
- **Deep Packet Inspection** - Layer 7 (Application Layer)

### **Advantages:**
- **Monitor Traffic** - A major responsibility of a firewall is to monitor the traffic passing through it. Whatever the information traveling through a network is in the form of packets. Firewall inspects each of these packets for any malicious threats. If any chance the firewall happens to find them it will immediately block them.
-  **Protection against Trojans** - A firewall in this instance will immediately block Trojans before they cause any damages to your system.
-  **Prevent Hackers** - Hackers on the internet constantly look for computers in order for carrying out their illegal activities. Firewall will based on security policy
-  **Access Control** - Firewalls comes with an access policy that can be implemented for certain hosts and services.
-  **Better Privacy** - By using a firewall many of the services offered by a site such as the domain name service and the finger can be blocked. Hence, the hackers are with no chance of getting privacy details

###**Note⚠️**
- **Packet-filtering** - Firewalls that only looked at headers



## <u>Honeypots</u> 🍯
*Honeypots that is designed to look like a real network, complete with multiple systems, databases, servers, routers and other digital assets. Since the honeynet, or honeypot system, mimics the sprawling nature of a typical network, it tends to engage cybercriminals for a longer period of time.*

*A honeypot trap can be manufactured to look like a payment gateway, which is a popular target for hackers because it contains rich amounts of personal information and transaction details, such as encoded credit card numbers or bank account information. *

*Once inside the network, it is possible to track cybercriminals’ movements to better understand their methods and motivations. This will help the organization adapt existing security protocols in order to thwart similar attacks on legitimate targets in the future.*

- **Honeynet** - Two or more honeypots on a network form a honeynet. Honeynets and honeypots are usually implemented as parts of larger Network Intrusion Detection Systems.

- A **Honeyfarm** is a centralized collection of honeypots and analysis tools.

### **Types of Honeypots:**
1. **Low-interaction** ---> Simulates/imitate services and systems that frequently attract criminal attention. They offer a method for collecting data from blind attacks such as botnets and worms malware. 
2. **High interaction** ---> Simulates all services and applications and is designed to be completely compromised
3. **Production** ---> Serve as decoy systems inside fully operating networks and servers, often as part of an intrusion detection system (IDS). They deflect criminal attention from the real system while analyzing malicious activity to help mitigate vulnerabilities.
4. **Research** ---> Used for educational purposes and security enhancement. They contain trackable data that you can trace when stolen to analyze the attack.

- **Honeypot Tools:**
  - Specter
  - Honeyd
  - KFSensor (Honeypot IDS)


> ⚠️ **Fragmentation is the heart of the IDS/Firewall Evasion techniques.**
---

## <u>Using SNORT</u>
*SNORT is an open source network intrusion detection system (NIDS). Snort is a packet sniffer that monitors network traffic in real time, scrutinizing each packet closely to detect a dangerous payload or suspicious anomalies.*

- Snort is a widely deployed IDS that is open source
- Includes a **sniffer**, **traffic logger** and a **protocol analyzer**
- Runs in three different modes
  - **Sniffer** - Watches packets in real time
  - **Packet logger** - Saves packets to disk for review at a later time
  - **NIDS** - Analyzes network traffic against various rule sets
- Configuration is in `/etc/snort` on Linux and `C:\snort\etc` in Windows; the file is **snort.conf**.

### **SNORT basics commands:**

**Operational modes:**
- Snort as **Sniffer** ---> `snort -v`

- Snort as **Packet logger**  ---> `snort -l`

- Snort as **NIDS** ---> `snort -A` or `snort -c <path_to_conf_file>`

**Example of usage**:

- **`snort -i 4 -l c:\Snort\log -c c:\Snort\etc\snort.conf -T`**
  - *This command will test snort configuration and rules and check if there is any erros without starting up.*
  - `-i 4` ---> interface specifier, in case is interface 4.
  - `-l` ---> for logging
  - `-c` ---> use Snort rules file specifying path
  - `-T` ---> Only For testing, this prevent Snort from start up; Essentially to check if there is any errors and if the rules are good.  

- **`snort -i 4 -c c:\Snort\etc\snort.conf -l c:\Snort\log -K ascii`**
  - *This command will fire up Snort NIDS and log everything in ASCII.*


### **SNORT Rules**
*SNORT has a rules engine that allows for customization of monitoring and detection capabilities.*

- **There are three available rule actions**
  1. Alert
  2. Pass
  3. Log
- **And three available IP protocols:**
  1. TCP
  2. UDP
  3. ICMP
