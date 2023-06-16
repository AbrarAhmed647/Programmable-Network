# Programmable-Network
CS6250  - A SDN programmable Network using P4 programming


In first task we have to enable connectivity between the two hosts in the topology depicted below. Additionally, we must configure the switches such that the traffic going from h1 to h2 uses the top path via s2 whereas the traffic from h2 to h1 uses the bottom path via s4.

To do this, we need to configure the switches to forward packets based on their ingress port number. For instance, when a packet enters port 1 on switch s1, it has to exit from port 2. The port numbers in the switches as well as the IP address of the hosts are indicated in the figure below.

![image](https://github.com/AbrarAhmed647/Programmable-Network/assets/56755432/586ca1e5-549c-48ab-9248-c2b9a6b8b6df)
