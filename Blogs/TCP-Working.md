# TCP Working : 3-Way Handshake

## Introduction to TCP / IP

**_Transmission Control Protocol_** or **_TCP_** is protocol that is used to communicate reliably over a network. TCP is present in the Transport Layer of the OSI Model. It’s main function is to transfer **data packets** (small segments of a data) in reliable manner. It ensures that the data packets are securely tranferred to the destination even over a unreliable network. IP is the internet protocol which is way to communicate to a device on a particular IP address.

## Problems solved by TCP

Real world networks are not reliable and can have many discrepancies. Some of the common problems of the networks are mentioned below :-

1. Packet Loss :- Data Packets can be lost during transmission.
    
2. Out-of-Order Delivery :- Packets take different routes, & can arrive in different order at the destination.
    
3. Data Corruption :- There can be corruption in data bits due to hardware and network faults.
    
4. Duplicate Packets :- Routers retransmits data packets and can cause data duplication.
    
5. Flow and Congestion :- Network may have high traffic and velocity.
    

These are some common problems which led to the design of TCP. We will later discuss how these problems are solved through TCP , but for now let’s discuss how the connection is established in TCP.

## The 3-way Handshake

The **3-way handshake** is the process used by TCP to **establish a connection** between a client and a server before any actual data is transferred.So both, the client and the server must agree to communicate and synchronize with each other.

This connection setup happens in **three steps**, hence the name _3-way handshake_.

### Step 1: SYN (Synchronize)

The process starts when the **client** wants to communicate with a server.

- The client sends a **SYN packet** to the server.
    
- This packet means: _“I want to establish a connection.”_
    

At this stage, no data is sent. Only a connection request is made.

### Step 2: SYN-ACK (Synchronize + Acknowledge)

When the **server** receives the SYN packet:

- It replies with a **SYN-ACK packet**.
    
- SYN means the server also wants to synchronize.
    
- ACK means the server has acknowledged the client’s request.
    

This packet means: _“I received your request and I am ready to communicate.”_

### Step 3: ACK (Acknowledge)

Finally, the **client** sends an **ACK packet** back to the server.

- This confirms that the client received the server’s response.
    
- Now both sides know that:
    
    - The other party is reachable
        
    - Both are ready to exchange data
        

After this step, the **TCP connection is successfully established**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769611099271/50a76587-00df-48f6-ba54-5ac019cc553b.png)

## How Data Transfer Works in TCP

Once the connection is established using the 3-way handshake, **data transfer begins**.

1. The data is divided into **small segments**.
    
2. Each segment is assigned a **sequence number**.
    
3. These segments are sent from sender to receiver.
    
4. The receiver sends back an **ACK (Acknowledgement)** for the received data.
    

TCP sends multiple segments at a time and waits for acknowledgment before sending more data. This makes the data transfer **controlled and reliable**.

## How TCP Ensures Reliability, Order, and Correctness

TCP uses multiple mechanisms to ensure correct data delivery.

1. ### Reliability
    

- If a packet is lost, the receiver does not send an ACK.
    
- The sender detects this and **retransmits** the missing packet.
    

2. ### Order
    

- Each packet has a **sequence number**.
    
- Even if packets arrive out of order, TCP rearranges them correctly.
    

3. ### Correctness
    

- TCP uses **checksums** to detect corrupted data.
    
- Corrupted packets are discarded and requested again.
    

Because of these mechanisms, TCP ensures that data is delivered **completely and correctly**.

## How TCP Connection Is Closed

When communication is finished, TCP closes the connection gracefully.

1. One side sends a **FIN packet** indicating it wants to close the connection.
    
2. The other side responds with an **ACK**.
    
3. Then the second side sends its own **FIN**.
    
4. Finally, the first side sends an **ACK**.
    

After this exchange, the connection is fully closed.

This process ensures that **all data is transmitted before termination**.

## Conclusion

TCP is a core protocol that enables reliable communication over unreliable networks. By using mechanisms like the 3-way handshake, acknowledgements, and controlled connection closure, TCP ensures that data is delivered correctly and in order. This reliability is why TCP is widely used in web applications and most internet services.