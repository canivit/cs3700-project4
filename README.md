# Project 4 - Realiable Transport Protocol

## My Approach:
Sender assigns unique IDs to every packet. Receiver stores and sends back an ACK for all packets it receives. When the receiver gets the EOF (end of file) packet, it sorts the packets according to their IDs and writes them to stdout. Sender uses slow start, additive increase for congestion avodiance, and multiple decrease when RTO expires. It also does the original TCP rtt estimation to estimate the latency with small modification: it only takes rtt samples for the first time pakcets are sent. It does not take rtt samples for retransmits.

## Challenges I Faced:
One challenge I faced was figuring out how to ensure EOF packets are not dropped, resulting in a time out. Then I found out that a simple brute force solution where the sender sends the EOF packet multiple times (20 in my case) would work. Another challenge was to configure congestion control and rtt estimation.
