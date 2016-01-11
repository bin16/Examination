# Points of Data and Computer Communications
*需要精简*
`DT-January 11, 2016 6:46 PM`

[TOC]


### II. GLOSSARY 名词解释

##### Stop-and-Wait Flow Control / Stop and Wait 停等协议 ppt-3 c7
> Stop-and-wait flow control is the simplest form of flow control. In this method, the receiver indicates its readiness to receive data for each frame, the message is broken into multiple frames. The sender waits for an ACK (acknowledgement) after every frame for specified time (called time out). It is sent to ensure that the receiver has received the frame correctly. It will then send the next frame only after the ACK has been received.
> *ppt-3 (7/48)*
>
> --------------------------
> Operations
Sender: Transmits a single frame at a time.
Receiver: Transmits acknowledgement (ACK) as it receives a frame.
Sender receive ACK within time out.
Go to step 1.
If a frame or ACK is lost during transmission then it has to be transmitted again by sender. This retransmission process is known as ARQ (automatic repeat request).
The problem with Stop-and-wait is that only one frame can be transmitted at a time and that often leads to inefficient transmission channel till we get the acknowledgement the sender can not transmit any new packet. During this time both the sender and the channel are unutilized.
> *ppt3 (8/48)*


##### Asynchronous Transmission 异步传输 ppt-2 c6
> The strategy with this scheme is to avoid the timing problem by not sending long, uninterrupted streams of bits. Instead, data are transmitted one character at a time, where each character is five to eight bits in length.1Timing or synchronization must only be maintained within each character; the receiver has the opportunity to resynchronize at the beginning of each new character.
> *ppt-2 (19/47)*

##### Synchronous Transmission 同步传输 ppt-2 c6
> *Or Asynchronous Transmission (Bit Oriented Transmission) means "面向位的传输"*
> With synchronous transmission, a block of bits is transmitted in a steady stream without start and stop codes.The block may be many bits in length.To prevent timing drift between transmitter and receiver, their clocks must somehow be synchronized. 
One possibility is to provide a separate clock line between transmitter and receiver. One side (transmitter or receiver) pulses the line regularly with one short
pulse per bit time.The other side uses these regular pulses as a clock.
> *ppt-2 (22/47)*

##### Flow Control 流量控制 ppt-3 p5
> Flow control is a technique for assuring that a transmitting entity does not overwhelm a receiving entity with data. 
The receiving entity typically allocates a data buffer of some maximum length for a transfer. When data are received, the receiver must do a certain amount of processing before passing the data to the higher-level software. In the absence of flow control, the receiver’s buffer may fill up and overflow while it is processing old data.
> *ppt-3 (5/48)*

##### SMTP (The Simple Mail Transfer Protocol)
> The Simple Mail Transfer Protocol (SMTP) is the standard protocol that a mail transfer program uses
SMTP can be characterized as:
- Follows a stream paradigm (TCP)
- Uses textual control messages
- Only transfers text messages (ASCII) – 7 bits/char
- Allows a sender to specify recipients’ names and check each name
- Sends one copy of a given message

> SMTP has a restriction to send only textual content
- MIME standard that allows email to include attachments such as graphic images or binary files

> SMTP can send a single message to multiple recipients 
- The protocol allows a client to list users and then send a single copy of a message for all users on the list
>
> *ppt-13 (67/79)*

##### HTML
> HyperText Markup Language (HTML) is a representation standard that specifies the syntax of a web page
HTML has the following general characteristics:
- Uses a textual representation   
- Describes pages that contain multimedia
- Follows a declarative rather than procedural paradigm
- Provides markup specifications instead of formatting
- Permits a hyperlink to be embedded in an arbitrary object
- Allows a document to include metadata
> *http://en.wikipedia.org/wiki/Metadata*
> 
HTML allows a programmer to specify a complex web page that contains graphics, audio, and video, as well as text
- We should have used hypermedia in the name instead of hypertext
>
> *ppt-13 (12/79)*


##### Domain Name System (DNS)
>  DNS provides a service that maps human-readable symbolic names to computer addresses
Provide name resolution services
- domain name <=> IP address
>
> Whenever an application needs to translate a name
- the application becomes a client of the naming system
- the client sends a request message to a name server
- server finds the corresponding address and sends a reply message
	- if it cannot answer a request, a name server temporarily becomes the client of another name server, until a server is found that can answer the request
>
> Name resolution
- Given a name, find its IP address
>
>
>*ppt-13 (32/79, 33/79, 34/79)*



##### Dynamic Host Configuration Protocol (DHCP)
> When a lease expires, a host can choose to relinquish the address or renegotiate with DHCP to extend the lease
- Negotiation occurs concurrent with other activity
>
> Normally, DHCP approves each lease extension
- A computer continues to operate without any interruption
- However, a server may be configured to deny lease extension for administrative or technical reasons
>
> *ppt-11 (45/63)*


##### Circuit Switching ^!E^
> 10.2 CIRCUIT-SWITCHING NETWORKS
Communication via circuit switching implies that there is a dedicated communication path between two stations. That path is a connected sequence of links between network nodes. On each physical link, a logical channel is dedicated to the connection. 
Communication via circuit switching involves three phases, which can be
1. Circuit establishment. Before any signals can be transmitted, an end-to-end (station-to-station) circuit must be established. 
2. Data transfer. Data can now be transmitted from the source station through the network to the target station. The transmission may be analog or digital, depending on the nature of the network. Generally, the connection is full duplex.
3. Circuit disconnect. After some period of data transfer, the connection is terminated, usually by the action of one of the two stations. 
> 
> *ppt-5 (6/34)*
> 
> -------------------------------------
> 10.3 CIRCUIT-SWITCHING CONCEPTS
A network built around a single circuit-switching node consists of a collection of stations attached to a central switching unit. The central switch establishes a dedicated path between any two devices that wish to communicate. The heart of a modern system is a digital switch. The function of the digital switch is to provide a transparent signal path between any pair of attached devices. Typically, the connection must allow full-duplex transmission.
The network interface element represents the functions and hardware needed to connect digital devices, such as data processing devices and digital telephones, to the network.
The control unit performs three general tasks. First, it  establishes connections. Second, the control unit must maintain the connection. Third, the control unit must tear down the connection, either in response to a request from one of the parties or for its own reasons.
> *ppt-5 (10/34)*

##### Packet Switching ^!E^
> **Packet switching** was designed to provide a more efficient facility than circuit switching for bursty data traffic. With packet switching, a station transmits data in small blocks, called packets. Each packet contains some portion of the user data plus control information needed for proper functioning of the network.
> *ppt-5 (2/48)*
>
> -------------------------------------
> **PACKET-SWITCHING PRINCIPLES**
As the circuit-switching network began to be used increasingly for data connections, two shortcomings became apparent:
• In a typical user/host data connection (e.g., personal computer user logged on to a database server), much of the time the line is idle. Thus, with data connections, a circuit-switching approach is inefficient.
• In a circuit-switching network, the connection provides for transmission at a constant data rate. Thus, each of the two devices that are connected must transmit and receive at the same data rate as the other.This limits the utility of the network in interconnecting a variety of host computers and workstations.
> *ppt-5 (19/34)*
>
> ------------------------------------------
> **Packet switching** is a digital networking communications method that groups all transmitted data – regardless of content, type, or structure – into suitably sized blocks, called packet.
Packet switching features delivery of variable bit rate data streams (sequences of packets) over a computer network which allocates transmission resources as needed using statistical multiplexing or dynamic bandwidth allocation techniques. When traversing network adapters, switches, routers, and other network nodes, packets are buffered and queued, resulting in variable delay and throughput depending on the network's capacity and the traffic load on the network.
> *ppt-5 (21/34)*
> 
> --------------------------------------
> **This approach has a number of advantages over circuit switching**:
• `Line efficiency is greater`, because a single node-to-node link can be dynamically shared by many packets over time.The packets are queued up and transmitted as rapidly as possible over the link. By contrast, with circuit switching, time on a node-to-node link is preallocated using synchronous time division multiplexing. Much of the time, such a link may be idle because a portion of its time is dedicated to a connection that is idle.
• `A packet-switching network can perform data-rate conversion.` Two stations of different data rates can exchange packets because each connects to its node at its proper data rate.
• `Usually do not reject packets.` When traffic becomes heavy on a circuit-switching network, some calls are blocked; that is, the network refuses to accept additional connection requests until the load on the network decreases. On a packet-switching network, packets are still accepted, but delivery delay increases.
• `Priorities can be used.` If a node has a number of packets queued for transmission, it can transmit the higher-priority packets first.These packets will therefore experience less delay than lower-priority packets.
> *ppt-5 (22/34)*
>
----------------------------------------------------
> **Comparison of Circuit Switching and Packet Switching**
W are concerned with three types of delay:
• Propagation delay: The time it takes a signal to propagate from one node to the next.This time is generally negligible.The speed of electromagnetic signals
through a wire medium, for example, is typically 2*108m/s.
• Transmission time: The time it takes for a transmitter to send out a block of data. For example, it takes 1 s to transmit a 10,000-bit block of data onto a 10-kbps line.
• Node delay: The time it takes for a node to perform the necessary processing as it switches data.
> *ppt-5 (30/34)*

##### Network Address Translation (NAT)
> - The Internet has expanded and addresses became scarce
	- subnet and classless addressing (CIDR) were introduced to help conserve addresses
- Another mechanism was invented that allows multiple computers at a site to share a single, globally valid IP address, known as Network Address Translation (NAT)
> 
- NAT provides transparent communication 
	- a host in the Internet always appears to receive communication from a single computer rather than from one of many computers at the site
- NAT runs as an in-line service 
	- It must be placed on the connection between the Internet and a site
- Most implementations embed NAT in another device 
	- such as a Wi-Fi wireless access point or an Internet router
>
> -------------------------------------------------------------
> **THE GOAL of NAT** is to provide the following illusions:
1. viewed from the Internet,  a site appears to consist of a single host computer with one valid IP address 
	- all datagrams sent from the site appear to originate from one host
	- and all datagrams sent to the site appear to be sent to one host
>
2. When viewed from a host in the site
	- the Internet appears to accept and route private addresses
>
> *ppt-11 (53/63, 54/63, 56/63)*
> - Private addressing is only used inside a site 
> - Before a datagram from the site can be allowed onto the Internet
	- NAT must translate the private IP into a globally valid IP address
- NAT must translate the globally valid IP address in an incoming packet to a private address 
	- before transferring a datagram to a host at the site

##### Pirate Address
> NAT solves the problem by using two types of addresses
- The NAT device itself is assigned a single globally-valid IP address
	- as if the NAT device were a host on the Internet
- Each computer at the site is assigned a unique private address
	- also known as a nonroutable address



### III. Calculation
##### IP地址分类
##### 路由算法，求最短路径
##### 不好说

### 施工中……


I. 18选择*2分=36 。。Problem填空 阅读PPT
II. 名词解释8*4分 
平等协议Stop and wait？ 
Sync……Trans……Async……异步和同步传输？？，同步和？？ 
FlowControl 
主要在应用层>Chapter4< SMTP ？HTML？
DNS（简述原理流程）....全称2分加一点解释 
DHCP全称PPT（P42，44下面)
第十章？XXX相对于PacketSWITCH？？？优点
NAT工作原理综述p52？p53？两种私有地址？P59综述一下P62提到？？
III. 计算题*6
IP地址分类，大题
路由算法Degestle算法？？求最短路径
HOMEWORK:<del>3,4,8</del>; 5前三; 7选择题无所谓什么鬼没说不一定没有IP地址分类类似问;题？？？; 6不知道;  2好几个题在这里,16，17，18，19;
ok, 就这样吧
Problem缩减范围