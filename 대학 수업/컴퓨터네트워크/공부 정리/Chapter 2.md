#### Identity
* Who are you? (identifier)
	Name
	Resident Registration Number
	Phone Number
	Email address (identifier @ address)
* Where are you? (locator)
	Address
	Domain Names

#### Internet Protocol Address
* IPv4 Address
	* Internet Protocol (RFC791) section 3.2
		Classful IPv4 Address (A,B,C)
	* Internet Standard Subnetting Procedure (RFC950)
		Address Mask
		The scheme of subnetting a class-A/B network number
	* Host Extensions for IP Multicasting (RFC1112)
		Ipv4 Multicast Address (D)
* IPv6 Address (RFC4291)

#### IPv4 Address

* The IPv4 addresses are **unique** and **universal**.
	An IP address is an address used to uniquely identify a device on an IP network.
* An IPv4 address is 32 bits long.
	32 binary bits are broken into four octets (1 octet = 8 bits)
	Notation
	1. Binary notation
	2. Dotted-decimal notation
	![[Pasted image 20240423023243.png|center|400]]

##### Example

* Change the following IPv4 addresses from binary notation to dotted-decimal notation vice versa.
	A. 10000001 00001011 00001011 11101111
	ans : 129.11.11.239
	B. 11000001 10000011 00011011 11111111
	ans : 
	C. 111.56.45.78
	D. 221.34.7.82
* Find the error, if any, in the following IPv4 addresses.
	A. 111.56.045.78
	B. 221.34.7.8.20
	C. 75.45.301.14
	D. 111000010.23.14.67

#### Classful IPv4 Address
![[Pasted image 20240423023725.png|center|400]]
* The address space is divided into five classes: A, B, C, D, and E.
##### Network / Host portion

* An IP address contains a network part and a host part.
	Identify the network
	Identify the host
	![[Pasted image 20240423024255.png|center|400]]

##### Hierarchical address
![[Pasted image 20240423024403.png|center|400]]

##### Hierarchical IPv4 address

* Usefulness of IP address management aspects. (allocation / distribution / registration)
	![[Pasted image 20240423024835.png|center|400]]
* Helps IP routing by facilitating identification of the destination network
* It enables a Hierarchical Routing.
	![[Pasted image 20240423024909.png|center|400]]

##### Classful IPv4 Address
* Class A: The first octet is the network portion. Octets 2, 3, and 4 are for subnets/hosts
* Class B: The first two octets are the network portion. Octets 3 and 4 are for subnets/hosts
* Class C: The first three octets are the network portion. Octet 4 is for subnets/hosts
* Class D: reserved for multicasting
* Class E: reserved for future use

##### Example
* Find the class of Each IPv4 Address
	1. 00000001 00001011 00001011 11101111 $\to$ class A
	2. 11000001 10000011 00011011 11111111 $\to$ class C
	3. 14.23.120.8 $\to$ class A
	4. 252.5.15.111 $\to$ class E
![[Pasted image 20240423025610.png|center|400]]


#### IPv4 Packet Forwarding Methods

* Unicast
* Broadcast
* Multicast
![[Pasted image 20240423025803.png|center|100]]
#### IPv4 Special Address

* 00000000 00000000 00000000 00000000
	All 0 :: Unspecified host (only valid as source address).
* 00000000 | Host
	Network part is all 0 :: A host on this network (only valid as source address).
* 127 | anything
	8-bit (1 octet) network part is 127 in decimal :: A local host (me), loopback addresses
* 11111111 11111111 11111111 11111111
	Broadcast on the local network (Limited broadcast)
	![[Pasted image 20240423030500.png|center|400]]
* Network | 11111111 … 11111111
	Broadcast on a distant network (Directed broadcast)
	![[Pasted image 20240423030629.png|center|400]]
* Limited broadcast vs Directed broadcast
	![[Pasted image 20240423030730.png|center|400]]

> [!gpt]
> IPv4의 특수 주소는 특별한 용도로 예약된 주소 범위입니다. 이러한 주소는 특정 네트워크 구성 요소 또는 특수한 통신 시나리오를 지원하기 위해 사용됩니다. 가장 일반적인 IPv4의 특수 주소에는 다음과 같은 것들이 있습니다:
>
>1. **IPv4의 특수 주소 유형**:
>
 >  - **Loopback Address (127.0.0.0/8)**:
 >    - 가장 흔히 사용되는 특수 주소입니다. 루프백 주소는 호스트 자신을 나타내는 데 사용됩니다. 대부분의 운영 체제에서는 127.0.0.1을 기본 루프백 주소로 사용하며, 이를 통해 호스트는 자체에 데이터를 보낼 수 있습니다.
>
 >  - **Private Address Space (10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16)**:
 >    - 사설 IP 주소 공간은 인터넷에서 공개되지 않은 사설 네트워크에 할당됩니다. 이러한 주소 범위는 인터넷에서 라우팅되지 않으므로 내부 네트워크에서만 사용됩니다.
>
 >  - **Broadcast Address (특정 네트워크의 마지막 주소)**:
 >    - 브로드캐스트 주소는 특정 네트워크 내의 모든 호스트에게 메시지를 전달하는 데 사용됩니다. 예를 들어, 192.168.1.255는 192.168.1.0/24 네트워크의 모든 호스트에게 메시지를 보내는 데 사용됩니다.
>
 >  - **Multicast Address (224.0.0.0/4 범위 내의 주소)**:
 >    - 멀티캐스트 주소는 특정 그룹의 멤버에게만 메시지를 전송하는 데 사용됩니다. 이는 라우터나 네트워크 장비의 다중 캐스트 지원에 사용됩니다.
>
 >  - **Reserved Addresses**:
 >    - 특정 목적을 위해 예약된 특수 주소가 있습니다. 예를 들어, 0.0.0.0은 기본 게이트웨이를 나타내며, 255.255.255.255는 브로드캐스트 주소입니다.
>
>이러한 특수 주소는 네트워크에서 특정 기능을 수행하는 데 사용되며, 각 주소는 고유한 용도와 제한 사항을 가지고 있습니다.

> [!gpt]
> Limited broadcast와 Directed broadcast는 네트워크에서 데이터를 전송하는 데 사용되는 두 가지 유형의 브로드캐스트 주소입니다. 이 두 주소 간에는 목적 및 사용 방법에 대한 중요한 차이가 있습니다.
>
>1. **Limited Broadcast**:
 >  - Limited broadcast 주소는 네트워크 상의 모든 호스트에게 메시지를 전달하는 데 사용됩니다.
>   - 이 주소는 로컬 네트워크 상의 모든 호스트에게만 메시지를 전송합니다. 즉, 메시지는 로컬 네트워크에만 한정되며, 라우터나 다른 네트워크로 전파되지 않습니다.
 >  - Limited broadcast 주소는 IPv4에서 255.255.255.255로 표시됩니다.
>
>2. **Directed Broadcast**:
 >  - Directed broadcast 주소는 특정 서브넷 또는 네트워크 상의 모든 호스트에게 메시지를 전달하는 데 사용됩니다.
>   - 이 주소는 특정 서브넷 또는 네트워크에 대한 메시지 전송을 지원하며, 라우터에 의해 다른 네트워크로 전파됩니다.
 >  - Directed broadcast 주소는 목적지 네트워크의 네트워크 주소 부분을 호스트 부분의 모든 비트로 설정하여 생성됩니다.
>   - 예를 들어, 네트워크 주소가 192.168.1.0이고, 서브넷 마스크가 255.255.255.0이라면, Directed broadcast 주소는 192.168.1.255가 됩니다.
>
>주의할 점은, Directed broadcast는 네트워크의 경계를 넘어 다른 네트워크로 전파될 수 있지만, Limited broadcast는 로컬 네트워크에서만 전파됩니다. 이러한 차이로 인해 두 주소의 사용 용도와 동작이 다릅니다.

* The intent of an IP directed broadcast is to flood the target subnet with the broadcast packets **without broadcasting to the entire network.**

* 10 | anything, 172 | 16 | anything, 192 | 168 | anything
	Used for local communications within a private network
	![[Pasted image 20240423031312.png|300]]
	![[Pasted image 20240423031329.png|300]]
	![[Pasted image 20240423031338.png|300]]

#### Scaling Issues in Routing
* Inefficient use of IP Address Space
	Class C with 2 hosts (2/254 = 0.78% efficient)
	Class B with 256 hosts (256/65534 = 0.39% efficient)
	IP address space gets consumed too quickly
* Too Many Networks
	Routing tables do not scale
	Router gets slower to scan a big forwarding table

> [!gpt]
> Classful IPv4 주소는 IPv4 주소 공간을 네트워크 클래스로 구분하는 방식을 의미합니다. 이것은 초기에 IPv4 주소가 배포되었을 때 사용되었던 방식입니다. Classful 주소 체계에서는 IPv4 주소가 세 가지 주요 클래스로 분류되었습니다: 클래스 A, 클래스 B 및 클래스 C.
>
>1. **클래스 A (Class A)**:
 >  - 클래스 A 주소는 첫 번째 비트가 0으로 시작하는 주소 범위입니다. 따라서 클래스 A 주소는 0.0.0.0에서 127.255.255.255까지의 범위를 갖습니다.
 >  - 클래스 A 주소의 첫 번째 옥텟은 네트워크 식별자이며, 나머지 세 개의 옥텟은 호스트를 나타냅니다.
 >  - 첫 번째 옥텟의 범위가 0에서 127까지이므로 클래스 A 주소는 매우 큰 네트워크를 지원할 수 있습니다.
>
>2. **클래스 B (Class B)**:
 >  - 클래스 B 주소는 첫 번째 비트가 10으로 시작하는 주소 범위입니다. 따라서 클래스 B 주소는 128.0.0.0에서 191.255.255.255까지의 범위를 갖습니다.
>   - 클래스 B 주소의 첫 번째 두 옥텟은 네트워크 식별자이며, 나머지 두 옥텟은 호스트를 나타냅니다.
 >  - 클래스 B 주소는 클래스 A보다는 작지만 여전히 중간 규모의 네트워크를 지원할 수 있습니다.
>
>3. **클래스 C (Class C)**:
 >  - 클래스 C 주소는 첫 번째 비트가 110으로 시작하는 주소 범위입니다. 따라서 클래스 C 주소는 192.0.0.0에서 223.255.255.255까지의 범위를 갖습니다.
>   - 클래스 C 주소의 첫 번째 세 옥텟은 네트워크 식별자이며, 마지막 옥텟은 호스트를 나타냅니다.
 >  - 클래스 C 주소는 작은 규모의 네트워크를 지원합니다.
>
>Classful IPv4 주소 체계는 네트워크 구성 및 관리를 단순화하기 위해 도입되었지만, 주소 부족 문제와 유연성 부족으로 인해 클래스리스 IPv4 주소 체계로 대체되었습니다. 클래스리스 체계에서는 주소 할당이 더 유연하게 이루어지며, VLSM (Variable Length Subnet Masking) 및 CIDR (Classless Inter-Domain Routing)와 같은 기술이 사용됩니다.

#### Subnetting - Concept

* Problem: Internet identifies only classes
* A subnet, or subnetwork, is a segmented piece of a larger network.
* Method: divide a large host space assigned for the network into sub-network
	![[Pasted image 20240423032328.png|center|400]]


> [!gpt]
> 서브넷 마스크(subnet mask)는 IP 주소의 네트워크 부분과 호스트 부분을 구분하는 데 사용되는 32비트의 이진 값입니다. 서브넷 마스크는 IP 주소와 함께 사용되어 네트워크의 크기를 정의하고, 각 주소가 어느 네트워크에 속하는지를 결정합니다.
>
>서브넷 마스크는 일반적으로 "255.255.255.0"과 같은 형식으로 표현되며, 이러한 형태는 네트워크 부분이 1로, 호스트 부분이 0으로 구성되어 있다는 것을 의미합니다. 이러한 마스크를 적용하면 IP 주소에서 네트워크 부분과 호스트 부분을 명확하게 구분할 수 있습니다.
>
>예를 들어, IP 주소가 "192.168.1.100"이고 서브넷 마스크가 "255.255.255.0"인 경우, 이 IP 주소는 192.168.1 네트워크에 속합니다. 서브넷 마스크의 각 비트가 1인 부분은 해당 IP 주소의 네트워크 부분을 나타내며, 각 비트가 0인 부분은 호스트 부분을 나타냅니다.
>
>서브넷 마스크는 IP 주소를 서브넷으로 나누는 데 사용되며, 서브넷의 크기를 조정하여 IP 주소 공간을 효율적으로 사용할 수 있습니다. 또한, 서브넷 마스크는 라우팅 및 네트워크 구성에 필요한 정보를 제공하며, 네트워크에서 호스트가 다른 호스트와 통신하는 방법을 결정하는 데 중요한 역할을 합니다.
#### Subnetting – How to Address

* Subnet masks define variable partition of host part
	![[Pasted image 20240423032501.png|center|400]]

#### Subnet Mask

* A subnetwork or subnet is a logical subdivision of an IP network.
	![[Pasted image 20240423032926.png|center|400]]
* Calculation : Example : 128.168.1.1/24
	1000 0000.1010 1000.0000 0001.0000 0001 - IP address
	1111 1111.1111 1111.1111 1111.0000 0000 - Subnet mask
	1000 0000.1010 1000.0000 0001.0000 0000 - Subnet network
	
	Number of hosts: 254 except for the reserved IDs (Host ID All 0 and Host ID All 1)

#### Classless Inter-Domain Routing (CIDR) (RFC4632)

* Basic Concept and Prefix Notation
	* The change from Class A/B/C network numbers to classless prefixes
		There is no class => no fixed network part size
	* In CIDR notation, a prefix is shown as a 4-octet quantity, followed by “/” and a decimal value between 0 and 32 that describes the number of significant bits.
		the legacy "Class B" network 172.16.0.0, with an implied network mask of 255.255.0.0
		(CIDR notation) 172.16.0.0/16

#### Subnetting – example

* Subnetting 211.100.10.0/24 network
* Each subnet must accommodate at least 60 hosts
	1. Subnet mask?
	Host bits = 6 bits ($2^{6}$ = 64, 64 – 2 (reserved) = 62 > 60)
	Subnet mask = 32 - 6 bits = 26 bits
	2. Number of Subnets
	Original network part = 24 bits, subnet => 26 – 24 = 2 bits = 22 = 4

#### Advantage of Subnetting

1. Detailed description of inner network structure 
2. Flexible allocation of a network
3. Efficient management of routing table entries
![[Pasted image 20240423041716.png|center|400]]
#### Transport Layer Address

* Unique Endpoint : 
	Network Layer Address + Port
		Network layer address distinguishes a host uniquely
		Port distinguishes a process uniquely in a local host
		Universally unique
* TCP or UDP connection identifier
	* UDP : <UDP, local endpoint, \*>
		<UDP, local IP, local port, any IP, any port>
	* TCP : <TCP, local endpoint, peer endpoint>
		<TCP, local IP, local port, peer IP, peer port>

> [!gpt]
> "Transport Layer Address"란 용어는 일반적으로 사용되지 않습니다. 하지만, 전송 계층(Transport Layer)은 네트워크에서 중요한 역할을 합니다.
>
>전송 계층은 송신자와 수신자 간의 통신을 관리하고 데이터 전송의 신뢰성과 효율성을 보장합니다. 주요 프로토콜로는 TCP (Transmission Control Protocol)와 UDP (User Datagram Protocol)가 있습니다.
>
>- **TCP (Transmission Control Protocol)**: 연결 지향적이며 신뢰성 있는 데이터 전송을 제공합니다. TCP는 데이터를 패킷으로 분할하고, 패킷을 송수신자 간에 신뢰성 있게 전달하고, 패킷의 순서를 관리하여 정확한 데이터 전송을 보장합니다. TCP는 각 연결에 대해 고유한 송신자 및 수신자의 IP 주소와 포트 번호를 사용하여 통신합니다.
>
>- **UDP (User Datagram Protocol)**: 비연결 지향적이며 신뢰성이 낮은 데이터 전송을 제공합니다. UDP는 데이터를 패킷으로 분할하고, 패킷을 송수신자 간에 전송합니다. 그러나 UDP는 데이터 전송의 성공 여부를 확인하지 않으며, 패킷의 손실이나 순서 변경을 처리하지 않습니다. UDP도 송신자 및 수신자의 IP 주소와 포트 번호를 사용하여 통신합니다.
>
>따라서 전송 계층은 데이터의 출발지 및 목적지를 식별하는 데 사용되는 IP 주소와 포트 번호를 사용하여 송신자와 수신자 간의 통신을 관리합니다. 이러한 정보를 이용하여 데이터 패킷이 올바른 대상으로 전달되고, 전송의 신뢰성과 효율성을 유지합니다.

#### Port Number

* The current assigned port numbers:
	https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml
* Port numbers are used to distinguish between different services that run over transport protocols such as TCP and UDP.

#### TCP Connection Identifier

> [!gpt]
> TCP 연결 식별자(TCP Connection Identifier)는 TCP 프로토콜에서 사용되는 고유한 값으로, 특정 TCP 연결을 식별하는 데 사용됩니다. TCP 연결은 송신자와 수신자 간의 가상적인 통신 경로를 나타내며, 이를 통해 데이터의 신뢰성과 순서를 보장합니다.
>
>TCP 연결 식별자는 TCP 헤더의 포트 번호와 IP 주소를 기반으로합니다. TCP 연결을 설정할 때, 송신자와 수신자는 각각 고유한 IP 주소와 포트 번호를 사용하여 연결을 식별합니다. 이를 통해 TCP 스택은 특정 TCP 연결을 식별하고, 연결된 데이터를 올바른 송신자와 수신자로 라우팅합니다.
>
>TCP 연결 식별자는 일반적으로 4개의 값으로 구성됩니다:
>
>1. **송신자 IP 주소**: TCP 연결을 초기화하는 측의 IP 주소입니다.
>2. **송신자 포트 번호**: TCP 연결을 초기화하는 측의 포트 번호입니다.
>3. **수신자 IP 주소**: TCP 연결을 수신하는 측의 IP 주소입니다.
>4. **수신자 포트 번호**: TCP 연결을 수신하는 측의 포트 번호입니다.
>
>이 네 가지 값의 조합은 TCP 연결 식별자를 형성하며, 이를 통해 TCP 스택은 특정 연결을 식별하고 관리합니다. TCP 연결 식별자는 데이터의 정확한 전송과 수신을 보장하는 데 중요한 역할을 합니다.

*  A message is successfully delivered only if all information in a connection identifier is matched
	![[Pasted image 20240423044248.png|center|500]]

#### UDP Connection Identifier

*  A message is successfully delivered if all information in a connection identifier is matched (Destination is me)
	![[Pasted image 20240423044544.png|center|500]]


> [!gpt]
> UDP (User Datagram Protocol)는 연결 지향적이지 않은 프로토콜이기 때문에 UDP 연결 식별자라는 개념은 존재하지 않습니다. TCP와는 달리 UDP는 연결 설정 및 유지를 관리하지 않고, 각각의 데이터그램이 독립적으로 처리됩니다. 
>
>UDP 패킷은 출발지 IP 주소와 포트 번호, 그리고 목적지 IP 주소와 포트 번호, 그리고 데이터를 포함합니다. 이러한 정보를 통해 데이터그램은 송신자와 수신자를 식별할 수 있습니다. 
>
>UDP에서는 연결을 설정하거나 연결 상태를 유지하지 않기 때문에 UDP 연결 식별자라는 것이 존재하지 않습니다. 각각의 UDP 패킷은 독립적으로 처리되며, 연관된 상태나 식별자를 가지고 있지 않습니다. 따라서 UDP는 TCP보다 더 빠르고 경량화된 데이터 전송을 위해 사용되며, 신뢰성 있는 전송이나 연결이 필요하지 않은 경우에 적합합니다.
