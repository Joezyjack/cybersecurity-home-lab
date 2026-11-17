
# Network Interface Discovery
  hostname
  ip link show
  ip addr show
  ip -br addr

# Routing
ip route
ip route get 8.8.8.8

# DNS Investigation
cat /etc/resolv.conf
getent hosts google.com

# Connectivity Testing
ping -c 4 192.168.100.1
ping -c 4 8.8.8.8

# Socket Inspection
ss -tuln
ss -tun
sudo ss -tulpn

# Nmap
nmap --version
nmap 127.0.0.1
nmap -sV 127.0.0.1
nmap -p- 127.0.0.1

# LAN Host Discovery
nmap -sn 192.168.100.0/24
netdiscover

