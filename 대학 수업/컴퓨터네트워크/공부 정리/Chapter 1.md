#### Protocol
* The rules that both the sender and receiver and all intermediate devices need to follow
- Why? To communicate effectively or achieve a specific objective.
* It is similar to a language
* Generally, a communication protocol must specify three aspects:
* 1. Message format
* 2. Order of message sent and received among network entities
* 3. Local action taken on messages transmission, reception
* Message format
* 1. Every protocol has its own message format. 
* 2. The role and purpose of the protocol are all specified within this message format (usually called header).
* Order of message sent and received among network entities
* Even when the message format is correct, the protocol will not work properly if the message is not sent in a well-defined sequence of protocol.
*  Local action taken on messages transmission, reception
* When a message arrives, it usually elicits some action(s) on the receiver’s part.
* After all, this is the ultimate purpose of any protocol.
* It could be the change of receiver state, or a message transmission in return, among others.

> [!gpt]
> 이 문서는 프로토콜에 대한 설명을 제공하고 있습니다.
>
>1. **프로토콜의 정의**:
 >  - 프로토콜은 효율적인 통신이나 특정 목표 달성을 위해 발신자, 수신자 및 중간 장치가 따라야 하는 규칙입니다. 이는 언어와 유사한 개념입니다.
>
>2. **프로토콜의 세 가지 측면**:
 >  - 프로토콜은 일반적으로 세 가지 측면을 명시해야 합니다:
 >    1. 메시지 형식: 각 프로토콜은 자체의 메시지 형식을 가져야 합니다. 이는 보통 헤더라고 불리는 메시지 포맷에 프로토콜의 역할과 목적을 명시합니다.
>     2. 메시지의 송수신 순서: 메시지가 프로토콜에 따라 어떤 순서로 송수신되어야 하는지 정의해야 합니다.
>     3. 메시지 전송 및 수신 시의 로컬 동작: 메시지가 전송되거나 수신될 때 수신자 측에서 어떤 동작이 발생해야 하는지를 명시해야 합니다. 이는 프로토콜의 최종 목적입니다.
>
>3. **프로토콜의 예시**:
 >  - 예를 들어, 인터넷 프로토콜(IP)은 메시지 형식(헤더), 메시지의 송수신 순서(IP 패킷의 라우팅), 그리고 메시지 전송 및 수신 시의 로컬 동작(IP 주소의 해석 및 패킷의 라우팅)을 명시합니다.
>
>이러한 프로토콜은 효율적이고 안정적인 통신을 위해 필수적입니다. 프로토콜은 네트워크와 통신 시스템이 정확하게 상호 작용하고 서로 이해할 수 있도록 함으로써 통신의 신뢰성을 보장합니다.

#### Protocol Layering
* What is the protocol layering?
	* Several protocols work together, but at different “levels” of working.
	* These levels are called “layer”
	* OSI 7-Layer Model vs TCP/IP protocol suit
	![[Pasted image 20240423012322.png|center|400]]

* Why the protocol layering is needed?
	Scenario 1 : Single layer protocol
	![[Pasted image 20240423012405.png|center|400]]
	Requirements 
	1. Greetings when they meet
	2. Select words based on their relationship
	3. You are silent when your opponent says
	4. When you break up, say goodbye
	
	Scenario 2 : 3-layer protocol
	![[Pasted image 20240423013355.png|center|400]]
	Requirements
	1. Communication is required at physically separate distances from each other.
	2. No changes should be made to the messages being sent or received.
	3. The message must be encrypted so that no one can see it except for the two.
	4. The transmission of the message must be guaranteed.

* Definition of protocol layering 
	Divide complex tasks into several small, simple tasks.
	* Advantages
		* Independent modularity between protocols is possible.
			* Independent updates for each protocol are possible. Just ensure the same output for the same input.
			* The inside of a protocol can be defined as a blackbox.
	* Disadvantages 
	1. Simple implementations can also be complicated

* Principles of protocol layering
	1. For bidirectional communication, each layer should be able to perform two opposite tasks.
		* {speaking / listening (writing / reading)},{encryption / decryption},{sending / receiving}
	2. The two objects under each layer at both sites should be identical
		![[Pasted image 20240423013651.png|center|400]]

#### ISO OSI 7 layers reference model
![[Pasted image 20240423013912.png|center|400]]
#### The Internet Protocol Stack
![[Pasted image 20240423014056.png|center|400]]
#### Application Layer
* The application layer is the top layer of the Internet protocol suite.
	It is the part that is visible to the user. An application running on the layer interacts directly with the user.
* Application layer provides platform to send and receive data over the network. 
* Example 
	Browsers :- Internet Explorer, Google Chrome

#### Transport Layer
* Provides transparent and reliable communication between two ends (applications), without being aware of what kind of network is used between the them.
	Responsible for the process-to-process delivery
	Example : TCP, UDP
	![[Pasted image 20240423014426.png|center|400]]
* Transport Layer – TCP vs UDP
	* Transmission Control Protocol (TCP)
		* Connection-oriented 
			* Provides in-sequence, reliable communication between processes
			* Handshake before communication
	* User Datagram Protocol (UDP)
		* Connectionless
			* Provides minimal functionality (Process-to-process)
			* No handshake

> [!gpt]
> 이 문서는 전송 계층의 두 가지 주요 프로토콜인 TCP와 UDP에 대한 설명을 제공하고 있습니다.
>1. **Transmission Control Protocol (TCP)**:
 >  - TCP는 연결 지향형 프로토콜입니다.
 >    - 이는 통신하기 전에 송수신측 간의 연결을 설정하는 것을 의미합니다.
 >  - TCP는 프로세스 간에 순서대로 신뢰할 수 있는 통신을 제공합니다.
 >    - 이는 데이터가 손실되지 않고 순서대로 전송되어야 하는 경우에 적합합니다.
 >  - 통신을 시작하기 전에 핸드쉐이크 과정을 거칩니다.
 >    - 이는 통신을 시작하기 전에 송수신측 간에 연결을 설정하는 과정입니다.
>
>2. **User Datagram Protocol (UDP)**:
 >  - UDP는 비연결형 프로토콜입니다.
 >    - 이는 통신하기 전에 연결을 설정하지 않는 것을 의미합니다.
 >  - UDP는 최소한의 기능만 제공합니다.
 >    - 이는 프로세스 간의 데이터를 전송하는 데 초점을 맞추어 작은 오버헤드를 갖습니다.
>   - UDP는 핸드쉐이크 과정이 없습니다.
 >    - 즉, 통신을 시작하기 전에 연결을 설정하지 않으므로 통신이 바로 시작됩니다.
>
>이를 요약하면, TCP는 신뢰할 수 있는 연결 지향형 통신을 제공하는 반면, UDP는 최소한의 기능을 가진 비연결형 통신을 제공합니다. TCP는 데이터의 신뢰성과 순서를 보장하기 위해 핸드쉐이크 및 연결 설정 과정을 거치지만, UDP는 이러한 과정이 없으므로 빠르게 통신을 시작할 수 있습니다.

#### Network Layer - IP
* All Internet transport protocols use the Internet Protocol (IP) to carry data from source host to destination host
* IP is a connectionless or datagram internetworking service which provides **no end-to-end delivery guarantees** 
	**Best effort Delivery**
* Internetworking
	* One of the main responsibilities of network layer is to provide internetworking between different networks.
	* It provides logical connection between different types of network. (Hardware-independent)
* Logical Addressing
	* In order to identify each device on internetwork uniquely, network layer defines an addressing scheme.
	* Such an address distinguishes each device uniquely and universally.
* Routing
	* When independent networks or links are combined together, multiple routes are possible from source machine to destination machine.
	* The network layer protocols determine which route or path is the best from source to destination.
		* It is known as routing.
		![[Pasted image 20240423015542.png|center|400]]

> [!gpt]
>이 문서는 네트워크 계층에서의 IP 프로토콜에 대한 설명을 제공하고 있습니다.
>
>1. **모든 인터넷 전송 프로토콜은 IP를 사용**:
 >  - 모든 인터넷 전송 프로토콜은 데이터를 출발지 호스트에서 목적지 호스트로 전달하기 위해 인터넷 프로토콜(IP)를 사용합니다.
>
>2. **IP는 연결 없는(datagram) 인터네트워킹 서비스를 제공**:
 >  - IP는 연결 없는(datagram) 인터네트워킹 서비스를 제공합니다. 이는 데이터의 끝-끝 전달을 보장하지 않는다는 것을 의미하며, 최선의 노력(best-effort) 전달을 제공합니다.
>
>3. **인터네트워킹**:
 >  - 네트워크 계층의 주요 책임 중 하나는 서로 다른 네트워크 간의 인터네트워킹을 제공하는 것입니다.
 >  - 이는 서로 다른 종류의 네트워크 간에 논리적인 연결을 제공합니다. 즉, 하드웨어에 독립적인 논리적인 연결을 제공합니다.
>
>4. **논리적 주소 할당**:
 >  - 인터네트워킹을 위해 각 장치를 고유하게 식별하기 위해 네트워크 계층은 주소 체계를 정의합니다.
 >  - 이러한 주소는 각 장치를 고유하고 범용적으로 구별합니다.
>
>5. **라우팅**:
 >  - 독립적인 네트워크나 링크가 결합되면 출발지 호스트에서 목적지 호스트로 가는 여러 경로가 가능합니다.
 >  - 네트워크 계층 프로토콜은 출발지에서 목적지까지의 최적 경로 또는 경로를 결정합니다. 이를 라우팅이라고 합니다.
>
>이를 요약하면, 네트워크 계층의 IP 프로토콜은 인터넷에서 데이터를 전달하는 데 핵심적인 역할을 하며, 인터네트워킹, 주소 할당 및 라우팅과 같은 중요한 기능을 수행합니다.

#### Datalink Layer
*  It is responsible for reliable hop-to-hop delivery of data. 
	* Framing
		Address
		Control information
	* Flow and error controls
	* Media Access Control
	![[Pasted image 20240423021036.png|center|400]]

> [!gpt]
> 이 문장은 데이터 링크 계층에 대한 설명으로 보입니다. 데이터 링크 계층은 네트워크에서 노드 간의 직접적인 통신을 담당하며, 다음과 같은 역할을 수행합니다:
>1. **Framing**:
 >  - 데이터 링크 계층은 전송되는 데이터를 프레임으로 나누어 관리합니다. 프레임은 시작과 끝을 식별하는 프레임 헤더와 특정 데이터를 포함하는 페이로드로 구성됩니다.
>
>2. **Addressing**:
 >  - 각 프레임에는 출발지 및 목적지 주소가 포함됩니다. 이것은 각각의 물리적인 장치를 식별하고, 목적지 장치로 프레임을 전달하는 데 사용됩니다.
>
>3. **Control Information**:
 >  - 데이터 링크 계층은 프레임에 대한 제어 정보를 포함합니다. 이 정보에는 오류 검출 및 수정을 위한 검사합, 흐름 제어를 위한 제어 비트 등이 포함될 수 있습니다.
>
>4. **Flow and Error Controls**:
 >  - 데이터 링크 계층은 데이터의 흐름을 제어하고 오류를 감지하고 수정하는 기능을 제공합니다. 이는 통신 중에 데이터 손실을 방지하고 데이터의 정확성을 보장하는 데 중요합니다.
>
>5. **Media Access Control (MAC)**:
>   - 물리적인 매체에 접속하여 데이터 전송을 관리합니다. 이는 다중 접속 네트워크에서 여러 장치가 동시에 데이터를 전송하고 충돌을 방지하기 위해 사용됩니다.
>
>이러한 기능들은 데이터 링크 계층이 네트워크에서 데이터의 신뢰성을 유지하고 효율적인 전송을 보장하는 데 중요한 역할을 한다는 것을 나타냅니다.

* Flow control
	Prevents the overflow in recipient
	![[Pasted image 20240423022029.png|center|400]]
* Error control
	Detect and fix an error (Missing a frame, wrong bit)
	![[Pasted image 20240423022107.png|center|400]]
* Media access control
	Prevent and control a collision
	![[Pasted image 20240423022142.png|center|400]]

#### Physical Layer
* The physical layer, the lowest layer of the OSI model, is concerned with the transmission and reception of the unstructured raw bit stream over a physical medium.
	Responsible for electrical signals, light signal, radio signals etc.
		Modulation
	Hardware-dependent layer of the OSI layer
![[Pasted image 20240423022322.png|center|400]]

#### Identifiers in networks
![[Pasted image 20240423022430.png|center|400]]
