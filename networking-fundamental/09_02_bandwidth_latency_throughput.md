# Bandwidth, Throughput, Latency, Jitter and Loss

## Bandwidth

The theoretical capacity of a link.

Example: a 1 Gbit/s Ethernet link.

## Throughput

The actual useful data rate achieved.

Throughput can be lower than bandwidth because of:

- congestion
- protocol overhead
- loss/retransmission
- device limitations
- application behavior

## Latency

Time required for data to travel from one point to another.

Major components:

- propagation delay
- transmission delay
- processing delay
- queueing delay

## Jitter

Variation in packet delay.

Important for real-time traffic such as voice/video.

## Packet loss

Packets fail to reach the destination.

TCP can often recover through retransmission; real-time UDP applications may behave differently.

## Mental model

A highway:

- bandwidth = number of lanes
- throughput = actual traffic delivered
- latency = travel time
- jitter = variation in travel time
- packet loss = vehicles disappearing from the route
