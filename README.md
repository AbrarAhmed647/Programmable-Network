# Programmable-Network
CS6250  - A SDN programmable Network using P4 programming


In first task we have to enable connectivity between the two hosts in the topology depicted below. Additionally, we must configure the switches such that the traffic going from h1 to h2 uses the top path via s2 whereas the traffic from h2 to h1 uses the bottom path via s4.

To do this, we need to configure the switches to forward packets based on their ingress port number. For instance, when a packet enters port 1 on switch s1, it has to exit from port 2. The port numbers in the switches as well as the IP address of the hosts are indicated in the figure below.

![image](https://github.com/AbrarAhmed647/Programmable-Network/assets/56755432/586ca1e5-549c-48ab-9248-c2b9a6b8b6df)


In second task, 
The goal now is to implement a packet loss detector and locator. More precisely, the implementation must detect full failures, which result in all packets being dropped,
but also gray failures, which are failures that result in only a tiny fraction of the packets being dropped because of e.g., malfunctioning hardware.

Besides detecting the failure, the system must locate the failure. It must infer on which switch-to-switch link packets were lost and in which direction of the link.

The implementation of the packet loss detector and locator must be as follows.

1.Every p4 switch in your network must count in the egress pipeline the packets that are sent by every of its interfaces;
2.Every p4 switch in your network must also count in the ingress pipeline the packets that are received from every of its interface;
3.The controller must regularily collect these counters and verify that the counters of two adjacent switches are identical (no failure) or different (failure).

Below is a simple exemple with two p4 switches. We focus on the packets going from s1 to s2.

![image](https://github.com/AbrarAhmed647/Programmable-Network/assets/56755432/c95cc20a-5dd5-4759-af76-9e8945cea040)

Switch s1 maintains a counter in the egress pipeline for the interface 2. It increases the counter when it sends a packet on that interface.
Switch s2 maintains a counter in the ingress pipeline for the interface 1. It increases the counter when it receives a packet on that interface.
The controller then regularily (e.g., every second) collects the counters, compares them, and resets them. If the counter values are different, the controller infers a failure and can locate it.
