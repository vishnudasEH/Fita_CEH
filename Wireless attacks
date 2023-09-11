## Terms


**Wireless network** is a computer network that uses wireless data connection between network 
nodes.

**Access Point**: Access Point (AP) or Wireless Access Point (WAP) is a hardware device that allows wireless connectivity to the end devices.

**Service Set Identifier (SSID)**: A 32 bit identification string of the Access Point, the AP's name. SSID inserted into the header of every data packet.

**Basic Service Set Identifier (BSSID)**: MAC address of the Access Point.

**ISM Band**: A frequency band dedicated to the Industrial, Scientific and Medical purpose.

### GSM

- Global System for Mobile Communication
- Generations: 2G (GSM), 3G (UMTS), 4G (LTE)
- Frequency: 900 MHz - 1800 MHz

### Wi-FI 

Wi-Fi is a local area networking technology based on the IEEE 802.11 standard.

#### Wi-Fi  Authentication

- Open authentication
- Shared Key authentication

##### Open Authentication

|               Client               |    |                     WAP              |
|:----------------------------------:|:--:|:------------------------------------:|
|          Probe Request             | -> |                                      |
|                                    | <- |          Probe Response              |
| Open System Authentication Request | -> |                                      |
|                                    | <- |  Open System Authentication Response |
|       Association Request          | -> |                                      |
|                                    | <- |      Association Response            | 

- The Probe Request is to discover the network
- The Probe Response contains the parameters (SSID, data rate, encryption, ...)
- The Open System Authentication Request (authentication frame) is to set authentication open, 
the sequence number is set to 0x0001
- The Open System Request Response's sequence number is 0x0002
- The Association Request contains the security parameters (choosen encryption, ...)
- The Association Response complete the associations process

##### Shared Key Authentication

|               Client               |    |                       WAP                   |
|:----------------------------------:|:--:|:-------------------------------------------:|
|      Authentication Request        | -> |                                             |
|                                    | <- | Authentication Response with Challenge Text |
|  Encrypted Challenge Response      | -> |                                             |
|                                    | <- |     Successful / Unsuccessful response      |

## Wireless threats

### Evil twin attack

- Also known as **client mis-association**
- 📝 A rogue access point outside the place with the legitimate one
- E.g. can lure the employees of the organization to connect with it
- Can be done using [Airsnarf](http://airsnarf.shmoo.com/)

#### Honeyspot attack

- Faking a well-known hotspot on a rogue AP
- E.g. as McDonald's or Starbucks free Wi-Fi spot

## Wi-Fi Countermeasures

- Change default parameters
- Disable remote login to wireless devices
- Wireless IPS deployment
- Use strong password
- Use the latest standards (WPA2 AES)
- MAC filtering
- Update software often
- Enable firewall
- Use network management software

### **Tools:**
- **Aircrack-ng Suite** - is a complete suite of tools to assess WiFi network security.
  1. **Monitoring:** Packet capture and export of data to text files for further processing by third party tools.
  2. **Attacking:** Replay attacks, deauthentication, fake access points and others via packet injection.
  3. **Testing:** Checking WiFi cards and driver capabilities (capture and injection).
      - **`airodump-ng`** - Airodump-ng is used for packet capturing of raw 802.11 frames and is particularly suitable for collecting WEP IVs (Initialization Vector) for the intent of using them with aircrack-ng. 
      - **`airmon-ng`** - Used to enable monitor mode on wireless interfaces.
      - **`aireplay-ng`** - Is used to inject frames (arp replay, deauthentication attack, etc).
      - **`aircrack-ng`** - Is an 802.11 WEP and WPA/WPA2-PSK key cracking program.
