# Python-security-tools
import socket

# This script checks for open ports on a target
target = "127.0.0.1" # This is your own computer (localhost)
ports = [21, 22, 80, 443] # Common ports: FTP, SSH, HTTP, HTTPS

print(f"--- Scanning {target} ---")

for port in ports:
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.settimeout(1) # Don't wait forever
    result = s.connect_ex((target, port)) # Try to connect
    if result == 0:
        print(f"[+] Port {port} is OPEN")
    else:
        print(f"[-] Port {port} is closed")
    s.close()
