# 🧠 DevOps Network Command Cheatsheet

A comprehensive cheatsheet of **network-related commands** for DevOps engineers – from **basic** troubleshooting to **advanced** network analysis.

---

## 📂 Table of Contents

- [Introduction](#introduction)
- [Basic Networking Commands](#basic-networking-commands)
- [Intermediate Tools](#intermediate-tools)
- [Advanced Networking Tools & Techniques](#advanced-networking-tools--techniques)
- [TCP/IP Utilities](#tcpip-utilities)
- [DNS Tools](#dns-tools)
- [HTTP Debugging](#http-debugging)
- [Security & Scanning](#security--scanning)
- [Monitoring & Tracing](#monitoring--tracing)
- [References](#references)

---

## 📘 Introduction

This cheatsheet is designed to help DevOps professionals quickly reference and utilize important networking commands for various use cases, including connectivity checks, DNS troubleshooting, HTTP debugging, packet tracing, and performance monitoring.

---

## 🟢 Basic Networking Commands

```bash
# Check network interface and IP address
ifconfig         # (Linux, deprecated in favor of `ip a`)
ip a             # Show all IP addresses

# Test connectivity
ping google.com  # Ping a domain

# Check route
traceroute google.com    # Trace route to a host (Linux)
tracert google.com       # Windows version

# DNS lookup
nslookup google.com
dig google.com

# Display routing table
route -n
ip route show

# Test open ports
telnet <host> <port>
nc -zv <host> <port>

# Network connection and listening services
netstat -tulnp     # List open ports (deprecated in favor of ss)
ss -tulnp          # Show sockets

# Monitor real-time traffic
iftop              # Real-time bandwidth per interface
nload              # Interface bandwidth usage

# Test download/upload speeds
curl -s https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py | python

# Packet analysis
tcpdump -i eth0 port 80   # Capture HTTP packets

# Detailed connection tracking
conntrack -L              # View connection tracking table (iptables/netfilter)

# Network performance testing
iperf3 -s                 # Start iperf3 server
iperf3 -c <host>          # Run client against iperf3 server

# TCP packet viewer
tshark -i eth0

# TCP retransmissions
ss -s

dig @8.8.8.8 google.com +short
host google.com

curl -I https://example.com           # Fetch headers
curl -X POST -d "key=value" https://api.example.com
http https://example.com              # From HTTPie (better curl)

# Use proxy with curl
curl -x http://proxy:port https://example.com

# Port scanning
nmap -sS -p 1-65535 <host>

# Scan for OS and services
nmap -A <host>

# Check for open ports in subnet
nmap -sn 192.168.1.0/24

# System network performance
sar -n DEV 1 5             # Network stats using sysstat

# Real-time system tracing
dstat -tn                  # Real-time network and CPU stats

# Distributed tracing (e.g., Jaeger, Zipkin) – see external tools




