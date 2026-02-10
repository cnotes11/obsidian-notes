### 💻 **Fundamentals of Computers – Line by Line **

1. ✅ **Computer** is an electronic machine.
    
2. ✅ It takes input, processes it, and gives output.
    
3. ✅ A computer works on the principle of **Input → Process → Output (IPO cycle)**.
    
4. ✅ It operates using hardware and software.
    
5. ✅ Hardware is the physical part of a computer (like monitor, CPU, keyboard).
    
6. ✅ Software is a set of instructions (like Windows, MS Word, browsers).
    
7. ✅ There are two types of software:  
      🔹 System Software (e.g., Windows, Linux)  
      🔹 Application Software (e.g., MS Word, VLC)
    
8. ✅ The **main units** of a computer are:  
      🔹 Input Unit  
      🔹 Central Processing Unit (CPU)  
      🔹 Memory Unit  
      🔹 Output Unit
    
9. ✅ The CPU has three parts:  
      🔹 ALU (Arithmetic Logic Unit) – Performs calculations  
      🔹 CU (Control Unit) – Controls all operations  
      🔹 Registers – Temporary storage
    
10. ✅ Memory is of two main types:  
      🔹 Primary Memory (RAM, ROM)  
      🔹 Secondary Memory (HDD, SSD, Pen drive)
    
11. ✅ Computers understand only **binary language (0 and 1)**.
    
12. ✅ Computers are fast, accurate, and can work for long hours.
    
13. ✅ But they have **no intelligence** or decision-making ability.
    

---

### 📌 Bonus: Characteristics of Computers

- **Speed** – Very fast
    
- **Accuracy** – Makes no mistakes
    
- **Automation** – Works without human help
    
- **Storage** – Can store huge data
    
- **Versatility** – Can perform many types of tasks


  ### 🧠 **BIOS (Basic Input/Output System)**

1. ✅ BIOS is the **older firmware** used to boot a computer.
    
2. ✅ It runs when the computer is powered on.
    
3. ✅ It performs **POST (Power-On Self Test)**.
    
4. ✅ BIOS is stored in a **ROM chip** on the motherboard.
    
5. ✅ It supports only **MBR (Master Boot Record)** partition style.
    
6. ✅ BIOS has a **text-based interface** (blue/black screen).
    
7. ✅ Limited to **16-bit mode**, can access only up to 1 MB memory during boot.
    
8. ✅ Booting speed is slower.
    
9. ✅ BIOS supports only **Legacy mode**.
    

---

### 💡 **UEFI (Unified Extensible Firmware Interface)**

1. ✅ UEFI is the **modern replacement** of BIOS.
    
2. ✅ It also starts when the computer is powered on.
    
3. ✅ UEFI is stored in **flash memory** on the motherboard.
    
4. ✅ It supports **GPT (GUID Partition Table)** – allows larger disks.
    
5. ✅ UEFI has a **graphical interface** and supports mouse input.
    
6. ✅ It works in **32-bit or 64-bit mode**, and can access more RAM.
    
7. ✅ Booting is **faster** compared to BIOS.
    
8. ✅ UEFI supports **Secure Boot** (for better security).
    
9. ✅ It is more flexible and powerful than BIOS.



  ## 💻 **Booting Process **

### ✅ 1. **Power On**

- When you press the **power button**, the computer starts.
    
- This process is called **booting**.
    

---

### ✅ 2. **POST (Power-On Self-Test)**

- The system first **checks hardware** components.
    
- Example: RAM, keyboard, hard disk.
    
- If there is a problem, you may hear a **beep sound** or see an error.
    

---

### ✅ 3. **BIOS/UEFI Loads**

- After POST, the system loads **BIOS or UEFI firmware**.
    
- It is stored on the **motherboard**.
    

---

### ✅ 4. **Boot Device Detection**

- BIOS/UEFI **finds the bootable device**.
    
- Example: Hard disk, SSD, USB, CD/DVD.
    

---

### ✅ 5. **Boot Loader Loads**

- The **boot loader** is loaded from the boot device.
    
- It is a small program that **starts the Operating System**.
    

---

### ✅ 6. **Operating System Loads**

- The boot loader loads the **Operating System (Windows/Linux)** into RAM.
    
- The system is now ready to run.
    

---

### ✅ 7. **Login Screen Appears**

- Once the OS is fully loaded, the **login screen** appears.
    
- You can now enter your **username and password** to use the computer.
    

---

## 🔄 **Types of Booting**

1. 🔌 **Cold Boot** – Starting the computer from a completely powered-off state.
    
2. 🔁 **Warm Boot** – Restarting the computer (like pressing Restart or Ctrl + Alt + Del).


 ## 🌐 **Network Fundamentals in Windows **

### ✅ 1. **What is a Network?**

- A **network** is a group of two or more computers connected to share data, resources, and devices.
    

---

### ✅ 2. **Types of Networks:**

- **LAN (Local Area Network)** – Small area like home, school.
    
- **WAN (Wide Area Network)** – Large area like internet.
    
- **MAN (Metropolitan Area Network)** – Covers a city.


## 🌐 **What is an IP Address in Windows **

---

### ✅ 1. **Definition**

- **IP address (Internet Protocol Address)** is a **unique number** assigned to every device connected to a network.
    
- It helps your computer **identify itself** and **communicate** with other devices.
    

---

### ✅ 2. **Format**

- IP addresses come in two versions:
    
    - **IPv4**: 4 sets of numbers (e.g., `192.168.1.1`)
        
    - **IPv6**: 8 groups of hexadecimal numbers (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)
        

---

### ✅ 3. **Types of IP Addresses**

- **Private IP**: Used **inside local networks** (e.g., home Wi-Fi, LAN)
    
- **Public IP**: Used on the **internet**, assigned by ISP
    
- **Static IP**: Fixed IP address (manual)
    
- **Dynamic IP**: Automatically assigned by DHCP
    

---

### ✅ 4. **How to Check IP Address in Windows**

#### ➤ Method 1: Using Command Prompt

bash

CopyEdit

`ipconfig`

- Shows IPv4, subnet mask, and default gateway.
    

#### ➤ Method 2: Settings

- **Settings → Network & Internet → Status → View hardware properties**
    

---

### ✅ 5. **What Does the IP Address Do?**

- Helps your device **send and receive data**.
    
- Acts like a **postal address** for your computer on the network.
    

---

### ✅ 6. **Components of an IP Address**

- Divided into two parts:
    
    - **Network ID** – Identifies the network.
        
    - **Host ID** – Identifies the device within the network.
        

Example: In `192.168.1.5`

- `192.168.1` = Network ID
    
- `5` = Host ID
    

---

### ✅ 7. **Dynamic vs Static IP in Windows**

- **Dynamic IP** is auto-assigned by DHCP (default setting).
    
- **Static IP** is manually configured:
    
    - Go to **Control Panel → Network and Sharing Center → Adapter Settings**
        
    - Right-click → Properties → IPv4 → Set manually
        

---

### ✅ 8. **Loopback IP (Special IP)**

- `127.0.0.1` is called the **Loopback IP**.
    
- It is used to test the **network card** or **localhost**.
    

---

### ✅ 9. **IP Classes (IPv4)**

|Class|Range|Use Case|
|---|---|---|
|A|1.0.0.0 to 126.255.255.255|Large networks|
|B|128.0.0.0 to 191.255.255.255|Medium networks|
|C|192.0.0.0 to 223.255.255.255|Small networks|

---

### ✅ 10. **IP Address Conflicts**

- When **two devices** have the **same IP**, network doesn't work properly.

  ## 🌐 **What is Classful Addressing?**

1. ✅ Classful addressing is a method to **divide IPv4 addresses into different classes**.
    
2. ✅ Introduced in the **early days of networking** (before CIDR).
    
3. ✅ Each class has a **fixed size and range**, based on the **first few bits** of the IP address.
    
4. ✅ It helps in **allocating IP addresses** to organizations based on their size.
    

---

## 📊 **IP Address Structure**

- IPv4 address is **32 bits**, written in **dotted decimal** format (e.g. `192.168.1.1`)
    
- Divided into **network ID** and **host ID**.
    

---

## 🧠 **Types of Classes in Classful Addressing**

|Class|Starting Bits|IP Range|Default Subnet Mask|Usage|
|---|---|---|---|---|
|A|0xxxxxxx|1.0.0.0 to 126.255.255.255|255.0.0.0|Large networks|
|B|10xxxxxx|128.0.0.0 to 191.255.255.255|255.255.0.0|Medium networks|
|C|110xxxxx|192.0.0.0 to 223.255.255.255|255.255.255.0|Small networks|
|D|1110xxxx|224.0.0.0 to 239.255.255.255|Not applicable|Multicasting|
|E|1111xxxx|240.0.0.0 to 255.255.255.255|Not applicable|Research and experimental|

---

## 📌 **Details of Each Class**

### ✅ Class A:

- Used by **very large organizations**.
    
- **1st octet** is for network, remaining **3 for hosts**.
    
- Supports **~16 million hosts per network**.
    

---

### ✅ Class B:

- Used by **medium-size organizations**.
    
- First **2 octets** are network, last **2 are hosts**.
    
- Supports **~65,000 hosts per network**.
    

---

### ✅ Class C:

- Used by **small networks** (offices, homes).
    
- First **3 octets** for network, last **1 for hosts**.
    
- Supports **254 hosts per network**.
    

---

### ✅ Class D:

- Used for **multicast communication** (e.g. live streaming).
    

---

### ✅ Class E:

- Reserved for **experiments and research**.
    

---

## 🔐 **Why Classful Addressing in Cyber Security?**

1. ✅ **Network Security Policies** depend on **IP ranges and subnets**.
    
2. ✅ Helps in **firewall configurations** using class-based IP filters.
    
3. ✅ Useful in **IP Whitelisting/Blacklisting** for securing servers.
    
4. ✅ Network scanning and penetration testing often use class-based segmentation.
    
5. ✅ Understanding IP classes helps track and secure **internal vs external IPs**.
    

---

## 🚫 Limitations of Classful Addressing:

- Wastes IP addresses (e.g., Class A gives too many).
    
- Fixed subnet sizes — not flexible.
    
- Replaced by **CIDR (Classless Inter-Domain Routing)** in modern networks.
    

---

## 🔓 **What is a Public IP Address?**

1. ✅ A **public IP** is the IP address assigned to your **device or router by the Internet Service Provider (ISP)**.
    
2. ✅ It is used to **identify your network on the internet**.
    
3. ✅ It is **unique globally** — no two devices in the world have the same public IP at the same time.
    
4. ✅ You can find your public IP by visiting websites like:
    
    arduino
    
    CopyEdit
    
    `https://whatismyipaddress.com`
    
5. ✅ Example: `103.28.10.45`
    

---

## 🔒 **What is a Private IP Address?**

1. ✅ A **private IP** is used **inside a local network (LAN)**.
    
2. ✅ It is assigned to devices like laptops, mobiles, printers within your home or office.
    
3. ✅ These IPs **cannot be accessed directly from the internet**.
    
4. ✅ Routers assign private IPs using **DHCP (Dynamic Host Configuration Protocol)**.
    
5. ✅ Example: `192.168.1.10`
    

---

## 📊 **Private IP Address Ranges**

|IP Class|Range|
|---|---|
|Class A|10.0.0.0 – 10.255.255.255|
|Class B|172.16.0.0 – 172.31.255.255|
|Class C|192.168.0.0 – 192.168.255.255|

> Any IP outside these ranges is a **public IP**.

---

## 🔐 **Why Important in Cybersecurity?**

- **Public IPs** are exposed to the internet → need **firewalls** and **security**.
    
- **Private IPs** are **protected by NAT** (Network Address Translation) — safer for internal communication.
    
- Cyberattacks target **public IPs**, not private ones.
    
- Security tools (like firewall, VPN) use IP types for rules.