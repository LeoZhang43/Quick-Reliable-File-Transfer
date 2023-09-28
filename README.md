# Quick-Reliable-File-Transfer
This is a reliable and quick file transfer protocol build on top of UDP/IP and tested under high packet loss environment.
The throughput of this procotol under a 200ms latency and 20% packet loss rate topology network is 20MB/sec compare to traditional TCP/IP cubic version is 180Kb/sec
This is the basic process of our protocol:
1. send the packet name and size and set buffer size according to BDP
2. created a hash table which as length as number of packets 
3. send each packet from sender side using UDP
4. check missing packets in receiver side and sent them back using TCP
5. repeta step 3 and 4 until all packets are being received
6. stop timestamp and count total throughput