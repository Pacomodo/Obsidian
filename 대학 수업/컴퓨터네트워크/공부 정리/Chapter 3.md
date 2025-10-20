#### IP Motivation
* The internet protocol provides for transmitting blocks of data called datagrams from sources to destinations.
	Sources and destinations are hosts identified by IP addresses.
* The internet protocol also provides for fragmentation and reassembly of datagrams, for transmission through "small packet" networks.
#### IPv4 Operation
* The internet protocol implements two basic functions: addressing and fragmentation.
	Routing, using IPv4 addressing scheme
	Fragmentation, to accommodate “small packet” networks
* Message format contains fields to achive a specific objective
	IPv4 Header format contains several fields for addressing and fragmentation.

#### IPv4 Header
![[Pasted image 20240423045858.png|center|400]]
* Version : 4 (IPv4)
* Header Length : the length of IPv4 header in 4-byte unit
	Header Length is 5 $\to$ 20 bytes
* Total Length : the length of the datagram including the IPv4 header.
	Total Length is 1500, Header Length is 5 $\to$ Payload (Upper-layer data) is 1480 bytes (1500 – 5 $\times$ 4)

> [!gpt]
> IPv4 헤더의 Header Length 필드는 헤더의 길이를 나타내는 4바이트의 필드입니다. 이 필드는 헤더의 크기가 몇 바이트인지를 나타내며, 최소값은 20바이트입니다. 
>
>IPv4 헤더는 최소한 20바이트의 고정된 길이를 가지며, 이는 필수 필드인 Version, Header Length, Type of Service, Total Length, Identification, Flags, Fragment Offset, Time to Live, Protocol, Header Checksum, Source Address, Destination Address가 포함됩니다.
>
>따라서 Header Length 필드의 기본값은 20바이트입니다. 이는 헤더에 추가적인 옵션 필드가 없을 때의 최소 크기를 의미합니다. Header Length 필드는 4비트로 표현되며, 이 값은 20바이트 단위로 표시됩니다. 따라서 헤더의 크기가 20바이트일 때, Header Length 필드는 5로 설정됩니다. (5 * 4 = 20)
>
>그러나 헤더에 옵션 필드가 추가되면 Header Length 필드의 값이 증가합니다. 이 필드의 최대 값은 15로 설정됩니다. 따라서 헤더의 최대 크기는 60바이트입니다. (15 * 4 = 60)

##### Type of Service
* The Type of Service is used to indicate the quality of the service (QoS) desired.
	Priority, Delay, Throughput, Reliability, Cost

> [!gpt]
> IPv4 헤더의 Type of Service (ToS) 필드는 서비스 유형을 나타냅니다. 이 필드는 IP 패킷의 우선순위와 서비스 품질을 지정하는 데 사용됩니다. Type of Service 필드는 다음과 같은 세 가지 주요 서비스를 나타낼 수 있습니다:
>
>1. **Precedence (우선순위)**: 우선순위는 패킷이 네트워크에서 얼마나 중요한지를 나타냅니다. 높은 우선순위의 패킷은 낮은 우선순위의 패킷보다 먼저 처리됩니다.
>
>2. **Delay (지연)**: 패킷이 목적지까지 도달하는 데 걸리는 시간을 나타냅니다. 낮은 지연을 요구하는 애플리케이션에 대해 이러한 패킷은 우선적으로 처리될 수 있습니다.
>
>3. **Throughput (처리량)**: 패킷 전송에 필요한 대역폭을 나타냅니다. 높은 처리량을 요구하는 애플리케이션은 더 높은 처리량을 지정하여 네트워크 리소스를 확보할 수 있습니다.
>
>이러한 서비스 요구 사항은 네트워크의 특성과 트래픽 패턴에 따라 다를 수 있습니다. Type of Service 필드를 사용하여 네트워크 장비는 패킷을 적절히 처리하고 전달할 수 있습니다. 
>
>IPv4에서는 이 필드가 더 일반적으로 사용되지 않으며, 대신 Quality of Service (QoS) 기능을 구현하는데 사용되는 다른 방법들이 더 많이 사용됩니다. 예를 들어, Differentiated Services (DiffServ)나 Integrated Services (IntServ) 등이 있습니다.

* Behavior-Aggregate(BA) Classification :
	Differentiated Service Code Point : It is a method of classifying traffic of similar characteristics into a class and assigning weight to each class to process the service. It is very easy and highly scalable, and it is the most widely used method at present.

> [!gpt]
> Behavior-Aggregate (BA) Classification은 네트워크 트래픽을 분류하는 방법 중 하나입니다. 이 방법은 특정 트래픽의 행동 패턴을 기반으로 패킷을 그룹화하여 분류합니다.
>
>BA Classification은 패킷의 속성과 행동에 초점을 맞추어 분류를 수행합니다. 이 방법은 트래픽의 특성을 통해 트래픽을 분석하고 행동에 따라 그룹을 형성합니다. 예를 들어, 특정 프로토콜을 사용하는 패킷, 특정 포트 번호를 사용하는 패킷, 또는 일정한 트래픽 패턴을 갖는 패킷을 식별하여 그룹화할 수 있습니다.
>
>BA Classification은 트래픽을 더 정확하게 분류하고 관리하는 데 도움이 될 수 있습니다. 이를 통해 네트워크 관리자는 특정 트래픽 유형에 대해 정책을 적용하거나 리소스 할당을 조정할 수 있습니다. 또한 보안 목적으로 특정 유형의 트래픽을 식별하고 차단하는 데 사용될 수도 있습니다.
>
>전통적인 패킷 필터링 방법과는 달리 BA Classification은 트래픽의 행동과 특성을 더 잘 이해하고 분류하기 때문에 더 정확한 분류를 제공할 수 있습니다. 이는 네트워크의 성능 향상 및 보안 강화에 도움이 될 수 있습니다.

> [!gpt]
> Differentiated Service Code Point (DSCP)는 IPv4 헤더의 서비스 유형을 지정하는 데 사용되는 6비트 필드입니다. DSCP는 IP 패킷의 우선순위 및 서비스 품질을 식별하기 위해 사용됩니다.
>
>DSCP 값은 Quality of Service (QoS) 정책을 구현하는 데 사용됩니다. 네트워크에서 데이터 패킷의 처리 우선순위를 지정하여 트래픽 관리, 대역폭 할당 및 우선순위 기반의 전송을 가능하게 합니다.
>
>DSCP 값은 6비트 필드로서 0부터 63까지의 값을 가질 수 있습니다. 이 값은 서비스 클래스를 나타내며, 다양한 서비스 클래스에 대해 다양한 DSCP 값이 할당됩니다. 일반적으로 높은 DSCP 값은 높은 우선순위를 나타내며, 이에 따라 해당 패킷은 네트워크에서 더 우선적으로 처리됩니다.
>
>DSCP 값은 패킷의 헤더에 설정되며, 네트워크 장비는 이 값을 기반으로 패킷을 적절히 처리합니다. 이를 통해 네트워크 관리자는 특정 서비스에 대한 우선순위를 지정하고, QoS 정책을 적용하여 네트워크 리소스를 효과적으로 관리할 수 있습니다.

![[Pasted image 20240423052108.png|center|400]]
![[Pasted image 20240423052224.png|center|400]]
* Class (Priority) : 000 ~ 111
	Best effort ~ Network Control
* Drop probability
	01 = Low, 10 = Normal, 11 = High
* ECN
	00 – ECN is not capable.
	10, 01 – ECN is capable.
	11 – A router has encountered congestion

> [!gpt]
> Differentiated Services Field는 IPv4 헤더의 서비스 유형을 지정하는데 사용됩니다. 이 필드는 주요 서비스 요구 사항에 따라 패킷을 분류하고 우선순위를 지정하여 네트워크에서 트래픽 관리를 수행합니다.
>
>IPv4 헤더의 Differentiated Services Field는 총 8비트로 구성되어 있습니다. 이 8비트는 6비트의 DSCP (Differentiated Services Code Point)와 2비트의 Explicit Congestion Notification (ECN) 필드로 나뉩니다.
>
>DSCP는 각각의 패킷이 받을 수 있는 서비스 등급을 지정하는 데 사용됩니다. 여기에는 패킷의 우선순위, 서비스 품질 및 트래픽 처리 방식에 관한 정보가 포함됩니다. 이를 통해 네트워크는 패킷을 다양한 클래스로 분류하고 적절한 서비스를 제공할 수 있습니다.
>
>ECN은 네트워크의 혼잡 상태를 감지하고 트래픽 조절을 위해 사용됩니다. ECN 비트가 설정되면 네트워크 장비는 혼잡 상태를 인식하고 이에 따른 조치를 취할 수 있습니다.
>
>이러한 Differentiated Services Field를 사용하여 네트워크는 서로 다른 트래픽 클래스의 요구 사항을 충족하고 서비스 품질을 관리할 수 있습니다. 따라서 Differentiated Services Field는 IPv4 네트워크에서 QoS를 구현하는 데 중요한 요소입니다.

> [!gpt] 
> ECN (Explicit Congestion Notification) 비트는 IPv4 헤더의 Differentiated Services Field에서 사용되는 2비트 중 하나입니다. 이 비트는 네트워크의 혼잡 상태를 표시하고 패킷이 혼잡을 감지했음을 나타냅니다.
>
>ECN 비트가 "00"으로 설정되면, 이는 패킷이 혼잡에 대한 정보를 전달하지 않는다는 것을 의미합니다. 따라서 이 패킷은 혼잡 제어를 위한 ECN 기능을 사용하지 않습니다.
>
>ECN 비트가 "00"으로 설정된 패킷은 혼잡 상태를 네트워크에 알리지 않으므로, 네트워크 장비는 패킷을 일반적인 방식으로 처리합니다. 이 패킷은 혼잡을 감지하지 못하고 일반적인 전송 방식에 따라 전달됩니다.
>
>따라서 ECN 비트가 "00"으로 설정된 패킷은 단순히 ECN을 사용하지 않는 일반적인 전송을 나타냅니다. 이러한 패킷은 혼잡 제어에 관여하지 않으며, 네트워크에서 혼잡을 처리하기 위한 추가 조치를 취하지 않습니다.

##### Time to live
* Time to live (TTL)
	The current hop limit which an IPv4 packet can pass through
	The value decrements whenever an IPv4 packet is forwarded.
	![[Pasted image 20240423052936.png|center|400]]
* If TTL is not used and the routing information in a router is wrong, an IPv4 packet will infinitely remain in the network.
	![[Pasted image 20240423053127.png|center|400]]

##### Protocol
* Protocol
	 * Identifier to present the upper-layer protocol which should process the payload of an IPv4 packet.
		ICMP : 1, TCP : 6, UDP : 17
	* Note that header and payload are just chunk of bytes (octets) from the viewpoint of the computer.
	* Protocols interpret them as defined by their message format.

> [!gpt]
> IPv4 헤더의 Protocol 필드는 전송 계층 프로토콜을 지정하는 데 사용됩니다. 이 필드는 IPv4 패킷이 전송되는 상위 계층 프로토콜을 나타내며, 해당 프로토콜을 사용하여 패킷의 데이터가 어떻게 처리되어야 하는지를 지정합니다.
>
>Protocol 필드는 8비트로 구성되어 있으며, 값은 0부터 255까지의 범위를 가집니다. 일반적으로 사용되는 몇 가지 프로토콜에는 다음과 같은 것들이 있습니다:
>
>1. **ICMP (Internet Control Message Protocol)**: 네트워크 상태 및 오류 메시지를 전송하기 위해 사용됩니다. 예를 들어, Ping 요청 및 응답은 ICMP 메시지를 사용하여 수행됩니다.
>
>2. **TCP (Transmission Control Protocol)**: 연결 지향적이고 신뢰성 있는 데이터 전송을 제공하는 프로토콜입니다. 대부분의 웹 브라우징, 이메일 및 파일 전송 등의 응용 프로그램은 TCP를 사용합니다.
>
>3. **UDP (User Datagram Protocol)**: 연결 지향적이지 않고 신뢰성이 없는 데이터 전송을 제공하는 프로토콜입니다. 음성 및 비디오 스트리밍, DNS 쿼리 등은 UDP를 사용할 수 있습니다.
>
>4. **IPv6 (Internet Protocol version 6)**: IPv4와 유사하지만 확장된 주소 공간과 보안 기능을 제공하는 네트워크 계층 프로토콜입니다.
>
>5. **GRE (Generic Routing Encapsulation)**: 한 네트워크에서 다른 네트워크로 패킷을 전송하는 데 사용되는 터널링 프로토콜입니다.
>
>Protocol 필드는 각각의 프로토콜에 고유한 값이 할당되어 있으며, 이 값은 IPv4 헤더의 Protocol 필드에 지정됩니다. 이를 통해 수신자는 패킷의 상위 계층 프로토콜을 식별하고 적절한 처리를 수행할 수 있습니다.

![[Pasted image 20240423053541.png|center|400]]
##### Header Checksum
* Header Checksum
	The value which can be used for bit error of an IPv4 packet header
	The checksum is initially calculated at the sender
		The receiver repeats the same calculation on the whole packet including the checksum.
		If the result is satisfactory, the packet is accepted; otherwise, it is rejected.
	However, TTL is included to calculate the checksum
		TTL value is modified at each router
	The checksum is recalculated at routers
	The checksum field is the 16-bit one’s complement of the one’s complement sum of all 16 bit words in the header.
	For purposes of computing the checksum, the initial value of the checksum field is zero.
* Header Checksum Calculation
	![[Pasted image 20240423054043.png|center|400]]
	![[Pasted image 20240423054117.png|center|400]]
	16비트씩 끊는다 $\to$ 다 더한다 $\to$ 보수를 취한다
	![[Pasted image 20240423054236.png|center|400]]

#### IPv4 Function : Fragmentation
* Fragmentation
	dividing the IP datagram into smaller IP datagrams to pass through “small size” networks
	![[Pasted image 20240423054518.png|center|400]]
* Maximum Transmit Unit (MTU)
	The maximum datagram size that can be sent without a segment on the network interface.
	![[Pasted image 20240423054616.png|center|400]]

> [!gpt]
> IPv4 프로토콜은 데이터그램의 전송을 위해 패킷을 조각내는 기능을 포함합니다. 이 과정을 Fragmentation이라고 합니다.
>
>IPv4 패킷은 최대 크기가 정해져 있습니다. 이를 Maximum Transmission Unit (MTU)라고 합니다. 일반적으로 MTU는 1500바이트입니다. 하지만 경로 상의 네트워크 장비나 네트워크 종류에 따라 MTU는 다를 수 있습니다.
>
>데이터그램이 송신자에서 목적지까지 전송되는 동안, 중간 라우터 또는 네트워크 장비가 데이터그램의 크기를 처리할 수 있는 MTU보다 큰 경우에는 데이터그램을 분할해야 합니다. 이렇게 분할된 데이터그램은 작은 조각으로 나누어져 전송됩니다.
>
>분할된 데이터그램은 일련의 조각으로 나누어지며, 각각은 원래 데이터그램의 일부를 포함합니다. 이러한 조각은 목적지에서 다시 조합되어 원래의 데이터그램으로 복원됩니다.
>
>Fragmentation은 데이터그램의 전송을 가능하게 하지만, 일반적으로 성능과 관련된 문제가 있을 수 있습니다. Fragmentation은 네트워크 오버헤드를 증가시키고, 조각화된 데이터그램을 재조합하는 데 추가적인 처리를 필요로 합니다. 또한 중간에 분실된 조각이 있다면 전체 데이터그램이 완전히 손상될 수 있습니다.
>
>따라서 IPv6에서는 Fragmentation을 최소화하기 위해 기본적으로 MTU가 크게 확장되었으며, 라우터에서 패킷을 조각내는 대신에 송신자에서 필요한 경우 패킷 크기를 조절하도록 권장합니다.

#### IPv4 Header

##### Identification
* Identification
	The identifier which indicates the original IP datagram of fragments
	An identifying value assigned by the sender to aid in assembling the fragments of a datagram at the receiver
	![[Pasted image 20240423055036.png|center|400]]
##### Flags
* Flags
	consist of two 1-bit flags
	![[Pasted image 20240423055116.png|center|400]]
	Do not fragment
		Set by the sender of the IPv4 datagram
		Intermediate routers can’t fragment the datagram even though fragmentation is needed to pass through a link.
	More fragments
		Set by fragmenters
		This flags indicates that this datagram is not the last fragment.
##### Fragmentation offset
* Fragmentation offset
	tells the receiver the position of a fragment in the original datagram
	Its unit is 8-octet. (Offset value 10 == 80 octets) 즉, 175라면 1400바이트

#### Fragmentation Example
![[Pasted image 20240423055425.png|center|500]]
Total length = Header + Payload = 20 + 4000 = 4020

#### Reassembly Example
* Reassembly
	collects fragments of which identification values are same.
	The order of fragments to be assembled follows their fragmentation offset values.
	![[Pasted image 20240423060008.png|center|500]]

#### IPv4 Header

##### Source / Destination address
* Source IP address (32-bit)
	indicates the IPv4 address of the IPv4 datagram “sender”
* Destination IP address (32-bit)
	indicates the IPv4 address of the IPv4 dataram receiver
	It is used for the **routing function at the IP layer**.

#### IPv4 : Routing

* It exploits the routing table
	Network :: Network prefix or IPv4 address
	Netmask :: Prefix length (If 32, Network means IPv4 address)
	Next hop :: IPv4 address of the next hop
	Interface # :: Number of the interface to be used to reach the next hop
	![[Pasted image 20240423060654.png|center|400]]
* Which routing entry should be used?
	**Longest Prefix Matching**
* Longest Prefix Matching
	Compares the destination IPv4 address and (Network/Netmask) of routing entries
	Among matched routing entries, selects the routing entry of which the netmask is the longest.
* Matching?
	Bitwise AND operation of destination IPv4 address and netmask of a routing entry
	Compare with the AND operation result and network of the routing entry
* Ex – Destination IPv4 address is 131.17.21.5
	![[Pasted image 20240423061012.png|center|500]]
	![[Pasted image 20240423061033.png|center|500]]
	![[Pasted image 20240423061051.png|center|500]]
	![[Pasted image 20240423061119.png|center|400]]
* Special routing entry
	0.0.0.0/0
	This routing entry is always matched with all destination IPv4 address
	Default gateway entry
* Direct Forwarding
	The destination is in the same (local) network
	Intermediate IPv4 device does not exist
	![[Pasted image 20240423061404.png|center|400]]
* Indirect Forwarding
	The destination is somewhere else
	Intermediate IPv4 devices are required to reach the destination
	![[Pasted image 20240423061447.png|center|400]]
* Direct forwarding? Indirect forwarding?
	Key : The destination is on the same (local) network?
	It can be determined by routing table entries
		Next hop is :: (unspecified) => Direct
		Next hop is specified => Indirect
	![[Pasted image 20240423061555.png|center|500]]
	It can be determined by using two materials
		The IPv4 address of the interface to forward the IPv4 packet
		The subnet mask (prefix length) of the interface to forward the IPv4 packet
	![[Pasted image 20240423061817.png|center|400]]
![[Pasted image 20240423061852.png|center|500]]

192.168.anything 형태이므로, private network임을 알 수 있음. next hop이 따로 지정되있지 않음 $\to$ direct forwarding
