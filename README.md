## Replace downloads

A Python script that intercepts HTTP requests for `.exe` files and redirects them to a specified URL, allowing for replacement of downloads on the target system.

### Features

- Intercepts HTTP requests for `.exe` files
- Redirects download requests to a custom URL

### Usage

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Daniel-Ikenna/replace_downloads
   ```

2. **Configure the Redirect URL**:
   Replace the `Location` URL in the script with your desired redirect URL.

3. **Set Up iptables**:
   Add an iptables rule to send packets to the netfilter queue:
   ```bash
   sudo iptables -I FORWARD -j NFQUEUE --queue-num 0
   ```

4. **Run the Script**:
   ```bash
   sudo python replace_downloads.py
   ```

5. **Reset iptables**:
   After use, clear the iptables rule:
   ```bash
   sudo iptables --flush
   ```

### Requirements

- Python 3.x
- `scapy` and `netfilterqueue` libraries (install via `pip install scapy netfilterqueue`)
- Superuser privileges (use `sudo`)

### Important Note

This tool is intended strictly for educational purposes. Do not use on networks or with files without proper authorization.

### Authors

- [Zaid Sabih](https://ie.linkedin.com/in/zaid-sabih-al-quraishi-5444a6127)
- [Uzoeshi Daniel](https://www.linkedin.com/in/daniel-ikenna-33b709235)
