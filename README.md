# tcp-backlog-analysis
TCP backlog experiment using hping3 and Wireshark
# TCP Backlog Queue Analysis

## Aim
To observe effect of traffic load on TCP backlog queue using hping3.

## Tools used
- Wireshark
- hping3
- Linux terminal

## Commands used

Normal traffic
sudo hping3 -S -p 8080 -i u100000 -c 20 <server-ip>

Medium traffic
sudo hping3 -S -p 8080 -i u20000 -c 100 <server-ip>

Heavy traffic
sudo hping3 -S -p 8080 -i u10000 -c 200 <server-ip>

## Observations

Normal load
All SYN packets received SYN-ACK.
No delay observed.

Medium load
Small delay observed.
Backlog started filling.

Heavy load
Backlog became full.
Some packets dropped or delayed.

## Conclusion
As traffic increases, backlog queue fills and server cannot handle all requests efficiently.
