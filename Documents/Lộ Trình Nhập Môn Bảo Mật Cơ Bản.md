## 1. ⚙️ Kiến Thức Nền Tảng

### a. Hệ Điều Hành (Operating System)

- Hiểu rõ hai hệ điều hành chủ yếu là Windows và Linux: cách tổ chức hệ thống file, phân quyền người dùng, quản lý tiến trình, quản lý dịch vụ và bảo mật cơ bản.
    
- Linux căn bản:
    
    - Các lệnh thường dùng: `ls`, `cd`, `chmod`, `chown`, `ps`, `sudo`, `kill`, `top`, `htop`, `netstat`, `ss`, `ip`, `grep`, `awk`, `sed`, `find`, `locate`.
        
    - Quản lý người dùng và quyền truy cập: `adduser`, `passwd`, `groups`, `usermod`, `chmod`, `chown`.
        
    - Quản lý service, log hệ thống: `systemctl`, `journalctl`, `service`, `syslog`, `logrotate`.
        

### b. Mạng Máy Tính (Computer Networking)

- Mô hình OSI và TCP/IP: hiểu các tầng và vai trò từng tầng.
    
- Giao thức phổ biến: IP, TCP, UDP, ICMP, DNS, DHCP, HTTP/HTTPS, FTP, SSH, Telnet, ARP.
    
- Khái niệm Subnetting, NAT, Gateway, DNS spoofing.
    
- Công cụ và lệnh cơ bản:
    
    - `ping`, `traceroute`, `ipconfig` / `ifconfig`, `netstat`, `ss`, `dig`, `nslookup`, `nmap`, `arp`.
        
    - Packet sniffing bằng Wireshark, phân tích gói tin TCP handshake, DNS truy vấn.
        

---

## 2. 🧰 Các Công Cụ Hacking Căn Bản

### a. Kali Linux / Parrot OS

- Hệ điều hành được xây dựng chuyên biệt cho pentest và ethical hacking.
    
- Các công cụ tích hợp sẵn:
    
    - `nmap`: quét cổng, phát hiện thiết bị mạng.
        
    - `hydra`: công cụ brute-force password hỗ trợ nhiều giao thức.
        
    - `wireshark`: phân tích lưu lượng mạng theo thời gian thực.
        
    - `burpsuite`: đánh giá bảo mật ứng dụng web, intercept request/response.
        
    - `metasploit-framework`: framework khai thác lỗ hổng.
        
    - `sqlmap`: tự động khai thác SQL Injection.
        

### b. Máy Ảo (Virtualization)

- Tạo môi trường an toàn để thực hành hacking:
    
    - Dùng VirtualBox, VMware để cài Kali.
        
    - Máy chủ mục tiêu: Metasploitable, DVWA, bWAPP, OWASP Juice Shop.
        
    - Snapshot trạng thái để rollback khi cần.
        

---

## 3. 💻 Kỹ Năng Lập Trình

### Ngôn Ngữ Nên Biết:

- **Python**: viết script, tự động hóa, exploit tool, socket programming.
    
- **Bash**: điều khiển hệ thống Linux, chạy các tập lệnh tự động hóa.
    
- **JavaScript**: rất quan trọng khi test web app (XSS, DOM injection...)
    
- **C/C++**: nghiên cứu malware, phân tích mã máy, exploit binary, buffer overflow.
    
- **HTML/CSS**: cần biết khi test ứng dụng web.
    

### Kỹ năng xử lý input:

- Regular Expression để lọc và xử lý dữ liệu
    
- Giao tiếp qua socket đơn giản để hiểu client-server
    
- Kỹ thuật lọc input và kiểm tra dữ liệu đầu vào
    

---

## 4. 🌐 Web Hacking Cơ Bản

### Kiến Thức Nền:

- HTTP request/response headers, method (GET/POST/PUT/DELETE), cookie và session.
    
- Các kỹ thuật kiểm tra form, query string, hidden field, URL manipulation.
    

### Các Lỗ Hổng Thường Gặp:

- SQL Injection (trích xuất dữ liệu từ cơ sở dữ liệu).
    
- XSS (Cross-site Scripting – chèn mã JavaScript).
    
- CSRF (giả mạo yêu cầu).
    
- File Inclusion (Local/Remote File Inclusion).
    
- Command Injection, Directory Traversal.
    

### Thực hành qua các lab:

- [DVWA](http://www.dvwa.co.uk/) – Web app có lỗ hổng giả lập.
    
- [bWAPP](http://www.itsecgames.com/) – Bao gồm hơn 100 lỗ hổng.
    
- [PortSwigger Labs](https://portswigger.net/web-security) – Chuyên sâu XSS, logic flaw, SSRF...
    
- [HackTheBox](https://www.hackthebox.com/), [TryHackMe](https://tryhackme.com/): môi trường CTF.
    

---

## 5. 🔐 Bảo Mật Căn Bản

### Kỹ thuật mã hóa:

- **Hashing**: MD5, SHA1, SHA256 (lưu mật khẩu, kiểm tra tính toàn vẹn).
    
- **Symmetric Encryption**: AES, DES.
    
- **Asymmetric Encryption**: RSA, sử dụng trong SSL/TLS.
    

### Ẩn danh & truy cập an toàn:

- Dùng Tor, VPN, proxychains để giấu IP thật.
    
- Dùng máy ảo khi thử các kỹ thuật có khả năng ảnh hưởng hệ thống.
    

### Social Engineering:

- Phishing: tạo trang login giả.
    
- OSINT (Open Source Intelligence): thu thập thông tin từ MXH, domain, leak DB.
    
- Pretexting, baiting, scareware.
    

---

## 6. 🧪 Gợi Ý Công Cụ Portable

### Network & Web:

- Wireshark Portable
    
- Zenmap
    
- Burp Suite Community Edition
    
- Fiddler Classic
    
- HTTP Toolkit (sniff HTTP request trên máy tính)
    

### Password & Cracking:

- John the Ripper
    
- Hashcat (GPU-based cracking)
    
- KeePass (quản lý mật khẩu an toàn)
    
- Cain & Abel (hỗ trợ sniffing + cracking LAN – legacy)
    

### System Monitoring:

- Process Hacker (quản lý tiến trình)
    
- Sysinternals Suite (Autoruns, TCPView, Procmon, PsExec...)
    
- NetLimiter (giới hạn, phân tích băng thông)
    

### USB & Rescue:

- Rufus (tạo USB boot)
    
- Ventoy (chạy nhiều file ISO từ USB)
    
- AnyDesk, TeamViewer Portable (hỗ trợ từ xa)
    
- 7-Zip Portable (giải nén đa định dạng)
    

---

## 7. 🏁 **Lộ Trình Học Hacking Căn Bản Từng Bước**

### 🎯 **Giai Đoạn 1: Làm Quen Môi Trường**

✅ Checklist:

-  Cài đặt **VirtualBox** hoặc **VMware**
    
-  Cài Kali Linux (bản mới nhất) lên máy ảo
    
-  Tạo snapshot hệ thống trước khi thao tác để dễ rollback
    
-  Làm quen với Terminal Linux: di chuyển, tạo file, sửa file, phân quyền (`cd`, `ls`, `chmod`, `nano`, `cp`, `mv`, `rm`)
    
-  Tìm hiểu cấu trúc file hệ thống Linux (`/etc`, `/var`, `/home`, `/tmp`...)
    

🔗 Tài liệu khuyên dùng:

- [LinuxCommand.org](http://linuxcommand.org/)
    
- [Kali Tools List](https://tools.kali.org/tools-listing)
    

---

### 📡 **Giai Đoạn 2: Cơ Bản Mạng Máy Tính**

✅ Checklist:

-  Học mô hình OSI – TCP/IP, phân biệt các tầng và giao thức
    
-  Hiểu cách hoạt động của IP, TCP, UDP, DNS, DHCP
    
-  Sử dụng `ipconfig`, `ifconfig`, `ping`, `traceroute`, `netstat`, `nslookup`
    
-  Cài Wireshark và bắt thử gói mạng thật
    
-  Phân tích HTTP Request và DNS Query
    

🔗 Gợi ý:

- [Wireshark Labs](https://gaia.cs.umass.edu/wireshark-labs/)
    
- [Subnetting Practice Site](https://subnettingpractice.com/)
    

---

### 💻 **Giai Đoạn 3: Học Lập Trình Dành Cho Hacker**

✅ Checklist:

-  Học Python: biến, hàm, if-else, vòng lặp, xử lý file
    
-  Làm mini tool: quét port, tạo brute-force login đơn giản
    
-  Học Bash: `for`, `while`, xử lý file log đơn giản
    
-  Làm script tự động backup/log checker nhỏ
    
-  Làm quen với JavaScript (DOM, alert, console.log) – phục vụ cho XSS
    

🔗 Nguồn học:

- [Python for Security](https://securitynik.blogspot.com/)
    
- [Hackers-Arise Python](https://www.hackers-arise.com/python-for-hackers)
    

---

### 🕸 **Giai Đoạn 4: Web Hacking Căn Bản**

✅ Checklist:

-  Cài và cấu hình **DVWA**, **bWAPP**
    
-  Hiểu HTTP GET/POST, cookie, session
    
-  Thực hành:
    
    -  SQLi cơ bản (Union-based, Error-based)
        
    -  XSS (stored + reflected)
        
    -  CSRF thực tế
        
    -  File Upload Bypass
        

🔗 Lab:

- [PortSwigger Web Academy](https://portswigger.net/web-security)
    
- [TryHackMe Web Fundamentals](https://tryhackme.com/room/webfundamentals)
    

---

### 📡 **Giai Đoạn 5: Mạng Nội Bộ & Quét Lỗ Hổng**

✅ Checklist:

-  Dùng `nmap` để quét mạng LAN
    
-  Thử các chế độ: `-sS`, `-sV`, `-O`, `-A`
    
-  Quét lỗ hổng với `nmap scripts` và `nikto`
    
-  Luyện khai thác Metasploitable 2 với Metasploit:
    
    -  Dịch vụ FTP, SSH, Samba
        
    -  Dịch vụ Web có lỗi (phpmyadmin, tomcat...)
        

🔗 Hướng dẫn:

- [Nmap Book](https://nmap.org/book/)
    
- [Metasploit Unleashed](https://www.offensive-security.com/metasploit-unleashed/)
    

---

### 🛡 **Giai Đoạn 6: Bảo Mật Căn Bản & Ẩn Danh**

✅ Checklist:

-  Tìm hiểu cách mã hóa: MD5, SHA256, AES, RSA (mã hóa ứng dụng vs mã hóa lưu trữ)
    
-  Dùng Tor Browser, cài proxychains trong Kali
    
-  Thử dùng VPN + proxy kết hợp
    
-  Tìm hiểu OSINT: thu thập thông tin từ Google, whois, social media
    

🔗 Nguồn:

- [CyberChef (công cụ mã hóa/giải mã online)](https://gchq.github.io/CyberChef/)
    
- [OSINT Framework](https://osintframework.com/)
    

---

### ⚔️ **Giai Đoạn 7: CTF & Thực Chiến**

✅ Checklist:

-  Tham gia TryHackMe: **Complete Beginner Path**
    
-  Dùng Burp Suite để bắt và chỉnh sửa request
    
-  Dùng SQLMap để tự động khai thác SQLi
    
-  Thử sức HackTheBox: chọn các box dễ như Lame, Legacy, Jerry
    

🔗 Practice:

- [TryHackMe](https://tryhackme.com/)
    
- [HackTheBox](https://hackthebox.com/)
    
- [PicoCTF](https://picoctf.org/)









---
## 8. 📚 Tài Nguyên Tham Khảo & Học Online

- [HackTheBox](https://www.hackthebox.com/) – CTF chuyên sâu
    
- [TryHackMe](https://tryhackme.com/) – Cấp độ từ cơ bản đến nâng cao
    
- [PortSwigger Academy](https://portswigger.net/web-security) – Học web security qua mô phỏng
    
- [OverTheWire Wargames](https://overthewire.org/wargames/) – Học Linux và kỹ năng khai thác
    
- [PicoCTF](https://picoctf.org/) – CTF cho người mới bắt đầu
    
- YouTube: LiveOverflow, HackerSploit, John Hammond
    
- Reddit: /r/netsec, /r/AskNetsec, /r/hacking
    
