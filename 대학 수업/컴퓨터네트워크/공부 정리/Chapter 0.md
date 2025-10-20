#### Fundamental Goal
The top-level goal for the DARPA Internet Architecture was to develop an effective technique for multiplexed utilization (internetworking) of existing interconnected networks.
DARPA 인터넷 아키텍처의 최상위 목표는 기존 상호 연결된 네트워크의 다중 활용(인터네트워킹)을 위한 효과적인 기술을 개발하는 것이었습니다.
> [!gpt]
> DARPA Internet Architecture는 DARPA(Defense Advanced Research Projects Agency)가 개발한 인터넷 프로토콜과 구조를 말합니다. DARPA는 인터넷의 초기 발전에 중요한 역할을 해왔으며, 그들의 연구와 개발은 현대의 인터넷을 형성하는 데 중요한 역할을 했습니다. DARPA Internet Architecture는 TCP/IP 프로토콜 슈트를 포함하며, 이는 현재도 인터넷에서 사용되는 주요 프로토콜입니다. 이 아키텍처는 인터넷을 네트워크로 연결하는데 사용되는 핵심 프로토콜과 구조를 정의합니다.
*  The components of the Internet were networks, which were to be interconnected to provide some larger service.
*  The technique selected for multiplexing was packet switching
*  The final aspect of this fundamental goal was the assumption of the particular technique for interconnecting these networks - The technique of store and forward packet switching
* 인터넷의 구성 요소는 네트워크로, 더 큰 서비스를 제공하기 위해 서로 연결되어야 했습니다.
* 멀티플렉싱을 위해 선택한 기술은 패킷 스위칭이었습니다.
* 이 기본 목표의 마지막 측면은 이러한 네트워크를 상호 연결하기 위한 특정 기술을 가정하는 것이었습니다. - 저장 및 전달 패킷 스위칭 기술
____
#### The fundamental structure of the Internet

A packet switched communications facility in which a number of distinguishable networks are connected together using packet communications processors called gateways which implement a store and forward packet forwarding algorithm.
게이트 웨이는 패킷 통신 프로세서를 사용해 수 많은 구분가능한 네트워크를 연결한 패킷 스위치 통신 시설입니다. 게이트 웨이는 패킷 포워딩 알고리즘을 구현한 것입니다.

> [!gpt] packet forwarding algorithm이 뭐야?
> 패킷 전달 알고리즘은 네트워크 장비가 데이터 패킷을 목적지로 전달하는 방법을 결정하는 알고리즘입니다. 이 알고리즘은 라우터, 스위치 및 다른 네트워크 장비에서 사용됩니다. 패킷 전달 알고리즘은 주어진 패킷의 목적지 주소를 검사하고 그 주소를 기반으로 다음에 어떤 인터페이스를 통해 전송할 것인지를 결정합니다.
> 
>가장 일반적인 패킷 전달 알고리즘 중 하나는 경로 검색 알고리즘인 라우팅 프로토콜을 사용하는 것입니다. 이러한 프로토콜은 네트워크에서 가장 적합한 경로를 찾아내는 데 사용됩니다. 예를 들어, RIP (Routing Information Protocol), OSPF (Open Shortest Path First), BGP (Border Gateway Protocol) 등이 있습니다. 이러한 프로토콜은 다양한 메트릭 및 조건을 고려하여 패킷이 목적지로 가는 최적의 경로를 결정합니다.
>
>또한 패킷 전달 알고리즘은 스위치와 같은 장비에서 내부적으로 사용되는 경우도 있습니다. 이러한 경우에는 패킷을 해당 장비의 다음 출력 포트로 전달하기 위한 전달 테이블이나 스위치 판단 규칙을 사용합니다. 이러한 알고리즘은 장비의 라우팅 테이블이나 스위치 테이블에 의해 결정됩니다.

![[Pasted image 20240422222507.png|center]]
Postal system을 생각해봅시다.
* Basic idea of Internetworking
* Layered Processing : Mail Address or Postal Code
![[Pasted image 20240422222612.png|center]]

> [!gpt] Layered Processing이 뭐야?
> 계층적 처리(또는 계층식 처리)는 시스템이나 소프트웨어에서 사용되는 설계 원칙 중 하나입니다. 이 원칙은 전체 시스템이나 소프트웨어가 여러 개의 계층으로 나뉘어져 있고 각 계층이 특정한 기능을 담당하도록 설계되어 있음을 의미합니다.
>
>계층적 처리는 일반적으로 OSI(Open Systems Interconnection) 모델 또는 TCP/IP 모델과 같은 네트워크 프로토콜에서 볼 수 있습니다. 이러한 모델에서는 각 계층이 특정한 역할을 수행하며, 상위 계층은 하위 계층에서 제공되는 서비스를 활용하여 자신의 기능을 구현합니다. 이러한 방식으로 계층화가 구현되면, 시스템의 복잡성이 줄어들고 유지 보수가 용이해지는 등의 장점이 있습니다.
>
>예를 들어, TCP/IP 프로토콜 스택은 다음과 같은 계층으로 구성됩니다:
>1. **물리 계층 (Physical Layer)**: 데이터를 전송하기 위한 물리적 매체를 다룹니다.
>2. **데이터 링크 계층 (Data Link Layer)**: 프레임 단위의 데이터 전송을 관리하고 오류 제어를 수행합니다.
>3. **네트워크 계층 (Network Layer)**: 라우팅 및 패킷 전달을 담당합니다.
>4. **전송 계층 (Transport Layer)**: 데이터의 신뢰성과 흐름 제어를 담당합니다.
>5. **세션 계층 (Session Layer)**: 세션 간의 통신을 설정, 유지 및 해제합니다.
>6. **표현 계층 (Presentation Layer)**: 데이터의 형식을 변환하고 암호화 및 압축을 수행합니다.
>7. **응용 계층 (Application Layer)**: 최종 사용자가 접하는 서비스를 제공합니다.
>
>이러한 계층화된 구조는 네트워크 통신의 효율성과 확장성을 향상시키는 데 기여합니다.

___
#### The second-level goals
 * Internet communication
1. must continue despite loss of networks or gateways.
2. must support multiple types (Quality of Service (QoS)) of communication services. 
3. accommodate a variety of networks. 
4. permit distributed management of its resources.
5. Cost-effective. 
6. Host attachment with a low level of effort. (Plug and Play)
7. The resources used in the Internet architecture must be accountable.
 * 인터넷 통신
1. 네트워크 또는 게이트웨이의 손실에도 불구하고 계속되어야 합니다.
2. 여러 유형의 통신 서비스(서비스 품질(QoS))를 지원해야 합니다. 
3. 다양한 네트워크를 수용할 수 있어야 합니다. 
4. 리소스의 분산 관리가 가능해야 합니다.
5. 비용 효율적이어야 합니다. 
6. 적은 노력으로 호스트 연결 가능. (플러그 앤 플레이)
7. 인터넷 아키텍처에 사용되는 리소스에 책임이 있어야 합니다.

> [!gpt]
> 이 규칙들은 "인터넷 아키텍처의 설계 원칙"을 설명하는 것으로 보입니다. 각 규칙은 인터넷의 구성, 운영, 및 관리를 위한 기본적인 요구사항을 나타내며 다음과 같은 내용을 포함합니다:
>
>1. **must continue despite loss of networks or gateways**: 네트워크나 게이트웨이의 손실에도 인터넷 서비스가 지속되어야 합니다. 즉, 인터넷은 내구성이 있어야 하며, 단일 포인트의 장애가 전체 시스템에 영향을 미치지 않아야 합니다.
>
>2. **must support multiple types (Quality of Service (QoS)) of communication services**: 다양한 품질의 통신 서비스를 지원해야 합니다. 이는 다양한 응용 프로그램과 서비스에 대한 요구를 충족하기 위한 것입니다.
>
>3. **accommodate a variety of networks**: 다양한 유형의 네트워크를 수용해야 합니다. 즉, 인터넷은 여러 다른 기술과 플랫폼에서 동작할 수 있어야 합니다.
>
>4. **permit distributed management of its resources**: 인터넷 자원은 분산 관리될 수 있어야 합니다. 다수의 조직이나 업체가 자원을 관리하고 사용할 수 있어야 합니다.
>
>5. **Cost-effective**: 비용 효율적이어야 합니다. 인터넷 서비스 및 자원의 제공과 관리는 비용 효율적으로 이루어져야 합니다.
>
>6. **Host attachment with a low level of effort. (Plug and Play)**: 호스트는 쉽게 네트워크에 연결되어야 합니다. 즉, 사용자가 최소한의 노력으로 네트워크에 연결할 수 있어야 합니다.
>
>7. **The resources used in the Internet architecture must be accountable**: 인터넷 아키텍처에서 사용되는 자원은 책임을 져야 합니다. 자원의 사용과 관리는 투명하게 관리되어야 하며, 적절한 사용과 관리가 보장되어야 합니다.
>
이러한 원칙들은 인터넷의 기본적인 설계와 운영 원칙을 나타내며, 인터넷의 성공과 안정성을 유지하기 위해 중요한 역할을 합니다.

> [!gpt] DARPA Internet Protocol의 Second goal에 대해서 알려줘.
> DARPA(Defense Advanced Research Projects Agency)의 인터넷 프로토콜의 두 번째 목표는 "interoperability"입니다. 이는 다양한 종류의 네트워크 및 컴퓨터 시스템이 상호 연결되고 통신할 수 있는 능력을 의미합니다.
>
>DARPA는 초기에 ARPANET이라는 프로젝트를 통해 여러 대학 및 연구소에 컴퓨터 네트워크를 구축하고 연결했습니다. 이후에 이를 통합하고 표준화하여 DARPA Internet Protocol이 만들어졌습니다. 이러한 프로토콜의 개발과 보급을 통해 다양한 네트워크 시스템이 상호 연결될 수 있었습니다.
>
>따라서 DARPA의 두 번째 목표는 다양한 종류의 컴퓨터 시스템과 네트워크 간에 효율적인 통신과 상호 운용성을 가능하게 하는 것이었습니다. 이것은 현재의 인터넷이 다양한 기술과 플랫폼에서 동작하며 전 세계적으로 연결되어 있는 것과 같은 개념과 관련이 있습니다.

___
#### Internet communication must continue despite loss of networks or gateways
1. The End-to-End Principle
* All complex functionalities are put into the end hosts
* The end hosts only knows the exact semantics of communications
2. Fate Sharing
* Active communication states at the end hosts
* No communication states at networks
* dumb network
* Network faults do not disturb the communication states.
1. 엔드투엔드 원칙
* 모든 복잡한 기능은 최종 호스트에 배치됩니다.
* 최종 호스트는 통신의 정확한 의미만 알 수 있습니다.
2. 운명 공유
* 엔드 호스트에서 활성 통신 상태
* 네트워크에서 통신 상태 없음
* 덤 네트워크
* 네트워크 오류는 통신 상태를 방해하지 않습니다.
![[Pasted image 20240422230303.png|center]]
> [!gpt] End-to-End principle이 뭐야?
> End-to-End Principle은 네트워크 디자인과 프로토콜 개발에 대한 중요한 설계 원칙 중 하나입니다. 이 원칙은 "맨 끝에서 맨 끝으로"라고 번역되며, 네트워크 시스템에서 처리되는 기능이 가장 끝단에 위치한 사용자나 애플리케이션에 가까이 있어야 한다는 것을 강조합니다.
>
>간단히 말해, End-to-End Principle은 중간에 있는 시스템이나 서비스가 사용자나 애플리케이션의 요구를 이해하지 않고 그 요구를 처리하지 않는 것이 중요합니다. 대신, 네트워크의 끝단에 위치한 시스템이나 애플리케이션이 필요한 기능을 처리하고, 중간에 있는 시스템은 단순히 데이터를 전달하는 역할만을 수행해야 합니다.
>
>이 원칙은 네트워크 시스템의 성능, 신뢰성 및 보안을 향상시킬 수 있습니다. 예를 들어, 데이터의 암호화는 End-to-End Principle을 준수하기 위한 한 가지 방법입니다. 데이터를 전송하는 동안 중간에 있는 시스템이 데이터를 볼 수 있더라도 데이터가 암호화되어 있으면 데이터의 내용을 이해할 수 없습니다.
>
>End-to-End Principle은 인터넷의 기본 설계 원칙 중 하나로 간주되며, TCP/IP 프로토콜 스택과 같은 프로토콜에서도 반영됩니다. 이 원칙을 준수함으로써 사용자가 안전하고 개인 정보를 보호할 수 있으며, 더 나은 서비스 품질을 제공할 수 있습니다.

> [!gpt] Fate Sharing이 뭐야?
> "Fate Sharing"은 시스템이나 서비스의 한 요소의 실패가 다른 요소에 영향을 미치는 것을 의미합니다. 즉, 시스템의 여러 구성 요소가 서로 종속되어 있어 하나의 구성 요소가 실패할 경우 다른 구성 요소도 영향을 받게 됩니다.
>
>이것은 주로 분산 시스템에서 발생하며, 한 요소의 장애가 전체 시스템의 가용성이나 신뢰성을 감소시킬 수 있습니다. 예를 들어, 클라우드 컴퓨팅에서는 하나의 가상 머신이나 서버가 과부하 상태에 놓이거나 다운되면 해당 서버에서 실행 중인 다른 가상 머신도 영향을 받을 수 있습니다. 이는 동일한 물리적 하드웨어를 사용하기 때문에 발생하는 현상입니다.
>
>Fate Sharing을 줄이기 위해 분산 시스템에서는 여러 가용 영역에 서비스를 배포하고 각 구성 요소 간에 격리 메커니즘을 구현하여 하나의 영역에서의 장애가 다른 영역으로 전파되는 것을 방지합니다. 또한, 영향을 최소화하기 위해 장애 복구 및 회복 기능을 갖추는 것도 중요합니다.

___
#### Internet communication accommodate a variety of networks
 1. It hides underlying network technologies from applications
 * IP over anything, anything over IP
 * It requires to interconnect many existing networks
 * For each OS, it requires a standard interconnection specification
 * Network provides minimal functionality
 * But it is very difficult to replace the IP itself
 * The “Curse of the Narrow Waist”
 1. 애플리케이션에서 기본 네트워크 기술을 숨깁니다.
 * 모든 것을 통한 IP, 모든 것을 통한 IP
 * 기존의 많은 네트워크를 상호 연결해야 합니다.
 * 각 OS마다 표준 상호 연결 사양이 필요합니다.
 * 네트워크는 최소한의 기능만 제공
 * 그러나 IP 자체를 대체하는 것은 매우 어렵습니다.
 * "좁은 허리의 저주"
![[Pasted image 20240422230932.png|center]]

> [!gpt] Curse of the Narrow Waist가 뭐야?
> "Curse of the Narrow Waist"는 네트워크 설계에서 발생하는 문제를 설명하는 개념입니다. 이 개념은 네트워크에서 데이터 흐름이 한 곳에 집중되는 현상을 나타냅니다. 네트워크 통신이 좁은 지점으로 집중되면 해당 지점이 병목 현상을 초래하여 전체 네트워크 성능을 저하시킬 수 있습니다.
>
>이 용어는 보통 인터넷의 물리적인 구조나 설계 문제를 설명할 때 사용됩니다. 예를 들어, 한 나라나 지역에서 인터넷 연결이 단일 백본 라우터나 단일 해저 케이블과 같은 한정된 지점을 통해 이루어질 경우, 해당 지점이 병목 지점이 될 수 있습니다. 이러한 경우, 데이터 흐름이 병목 지점을 통과할 때 지연과 속도 저하가 발생할 수 있습니다.
>
>"Curse of the Narrow Waist"는 네트워크 설계자들이 데이터 흐름을 분산시키고 병목을 피하기 위해 적절한 백본 인프라를 구축하는 중요성을 강조합니다. 분산된 네트워크 구조를 구현하고 여러 경로를 통해 데이터를 전달하는 것은 전체 시스템의 가용성과 성능을 향상시키는 데 도움이 될 수 있습니다.

___
#### Internet communication permit distributed management of its resources

Each connected network may be independently managed as a set of independent “Autonomous Systems (AS)”
* Interior Routing
Exploit the detailed network topology to forward packets within an AS
OSPF
* Exterior Routing
Hide the detailed network topology as much as possible to forward packets between ASs
BGP (Border Gateway Protocol) connects ASs together
연결된 각 네트워크는 독립적인 "자율 시스템(AS)" 집합으로 독립적으로 관리할 수 있습니다.
* 내부 라우팅
세부 네트워크 토폴로지를 활용하여 AS 내에서 패킷을 전달합니다.
OSPF
* 외부 라우팅
세부 네트워크 토폴로지를 최대한 숨겨 AS 간에 패킷을 전달합니다.
BGP(보더 게이트웨이 프로토콜)는 AS를 서로 연결합니다.


> [!gpt] Autonomous Systems (AS)이 뭐야?
> 자율 시스템(Autonomous System, AS)은 인터넷에서 라우팅을 수행하는 일련의 네트워크와 라우터로 구성된 하나의 관리 도메인입니다. 각 자율 시스템은 단일 관리자나 관리 그룹에 의해 제어되며, 고유한 네트워크 주소 공간을 가지고 있습니다. AS는 네트워크 트래픽을 교환하고 라우팅 결정을 내리는 데 사용됩니다.
>
>일반적으로 자율 시스템은 하나 이상의 인터넷 서비스 제공업체(ISP), 대학, 기업 또는 기타 조직으로 구성되어 있습니다. 각 AS는 BGP(Border Gateway Protocol)와 같은 외부 라우팅 프로토콜을 사용하여 인터넷 상의 다른 AS와 통신합니다. AS는 독립적으로 라우팅 결정을 내리고 자체 네트워크를 관리할 수 있으며, 다른 AS와의 통신을 위해 ISP나 다른 AS를 통해 트래픽을 전송할 수 있습니다.
>
>AS는 네트워크 관리 및 보안, 트래픽 엔지니어링, 서비스 수준 계약(SLA) 등의 목적으로 사용됩니다. 또한 AS는 인터넷의 확장 가능성과 안정성을 유지하기 위한 중요한 요소입니다. 자율 시스템 간의 효율적인 트래픽 라우팅은 인터넷 전체의 안정성과 성능에 영향을 미칩니다.

> [!gpt] OSPF가 뭐야?
> OSPF(Open Shortest Path First)는 네트워크에서 내부 라우팅 프로토콜로 사용되는 라우팅 프로토콜입니다. OSPF는 라우터 간에 경로 정보를 교환하여 네트워크의 최적 경로를 계산하고 데이터 패킷을 전달하는 데 사용됩니다. 이는 TCP/IP 네트워크에서 사용되며, 주로 대규모의 기업 네트워크나 인터넷 서비스 제공 업체(ISP)의 네트워크에서 활용됩니다.
>
>OSPF는 링크 상태 라우팅 프로토콜입니다. 이는 각 라우터가 자신과 직접 연결된 링크의 상태 정보를 교환하여 네트워크 토폴로지를 구성하고, 각 라우터 간의 최단 경로를 계산하는 방식입니다. OSPF는 다양한 메트릭(대역폭, 지연, 비용 등)을 고려하여 경로를 선택하고 라우팅 테이블을 유지합니다.
>
>OSPF는 네트워크의 변화에 따라 동적으로 경로를 업데이트하고 트래픽 로드 밸런싱을 수행하여 효율적인 네트워크 성능을 유지합니다. 또한 OSPF는 계층화된 디자인을 지원하며, 다양한 네트워크 환경에 유연하게 적용될 수 있습니다.
>
>OSPF는 효율적인 네트워크 운영을 위해 다양한 기능과 옵션을 제공하며, 복잡한 네트워크에서도 안정적으로 동작합니다. 따라서 OSPF는 대규모 네트워크 환경에서 많이 사용되는 널리 알려진 내부 라우팅 프로토콜 중 하나입니다.

> [!gpt] BGP가 뭐야?
> BGP(Border Gateway Protocol)는 인터넷에서 사용되는 외부 라우팅 프로토콜입니다. BGP는 자율 시스템(Autonomous System, AS) 간에 경로 정보를 교환하고 인터넷의 전체적인 라우팅 테이블을 유지하는 데 사용됩니다.
>
>BGP는 TCP/IP 프로토콜 스택의 일부로 동작하며, AS 간에 경로 정보를 교환하여 데이터 패킷이 목적지까지 가장 효율적인 경로를 따를 수 있도록 지원합니다. 이러한 경로 정보는 AS의 경계에서 교환되며, 각 AS는 자체 내부 라우팅 프로토콜(예: OSPF, EIGRP 등)을 사용하여 내부 네트워크의 경로를 결정합니다.
>
>BGP는 매우 유연한 프로토콜로, 다양한 정책과 필터링 기능을 지원합니다. 이를 통해 네트워크 관리자는 트래픽의 흐름을 조절하고 인터넷 연결의 안정성과 보안을 유지할 수 있습니다. 또한 BGP는 대규모의 네트워크 환경에서 안정적으로 동작하며, 인터넷 서비스 제공 업체(ISP)뿐만 아니라 기업 네트워크에서도 널리 사용됩니다.
>
>요약하면, BGP는 인터넷의 핵심 인프라에서 사용되는 중요한 라우팅 프로토콜로서, 다양한 AS 간에 경로 정보를 교환하여 데이터 트래픽을 전달하는 데 사용됩니다.

___
#### Internet communication must be Cost-effective

* Circuit Switching
Exclusively occupying network resource for a connection
Requiring signaling for network resource allocation
* Packet Switching
Sharing network resource among connections
Requiring packetization
Each packet must carry information for routing
Causing more end-to-end transmission delay
* 회로 교환
연결을 위한 네트워크 리소스 독점 사용
네트워크 리소스 할당을 위한 시그널링 필요
* 패킷 교환
연결 간 네트워크 리소스 공유
패킷화 필요
각 패킷은 라우팅을 위한 정보를 전달해야 함
종단 간 전송 지연 증가


> [!gpt] circuit switching과 packet switching이 뭐야?
> Circuit switching과 Packet switching은 통신 네트워크에서 데이터를 전달하는 두 가지 주요한 방법입니다.
>
>1. **Circuit Switching (회선 교환)**:
>   - Circuit switching은 통신 경로를 설정하여 데이터를 전달하는 방식입니다.
 >  - 통신 세션을 시작할 때, 송신자와 수신자 사이에 전용 경로(회선)가 설정됩니다.
 >  - 데이터는 고정된 경로를 통해 전송되므로 대역폭이나 속도가 일정합니다.
 >  - 전화 네트워크가 가장 흔한 예시입니다. 전화를 걸면 회선이 확보되고, 통화가 끝날 때까지 해당 회선이 유지됩니다.
>
>2. **Packet Switching (패킷 교환)**:
>   - Packet switching은 데이터를 작은 패킷으로 나누어 전송하는 방식입니다.
 >  - 데이터는 송신자에서 수신자로 직접적인 경로가 설정되는 것이 아니라, 네트워크를 통해 여러 경로를 통해 전송됩니다.
 >  - 각 패킷은 독립적으로 전송되며, 목적지에 도착하면 재조립됩니다.
 >  - 인터넷과 같은 데이터 네트워크에서 주로 사용됩니다. 패킷 스위치나 라우터를 통해 전송되며, 각 패킷은 최적의 경로를 따라 전달됩니다.
>
> 두 방식은 각각의 장단점을 가지고 있습니다. Circuit switching은 연결을 설정하고 유지하기 위해 리소스가 필요하지만, 일단 연결이 설정되면 전송이 신뢰적이고 고정된 대역폭을 제공합니다. 반면에 Packet switching은 유연성이 있고, 여러 사용자가 동시에 네트워크를 공유할 수 있지만, 패킷이 여러 경로를 통해 전송되므로 도착 시간이나 순서가 보장되지 않을 수 있습니다.

|        서킷 스위칭        |        패킷 스위칭        |
| :------------------: | :------------------: |
| No Store and Forward |  Store and Forward   |
|    Dedicated link    |     Shared link      |
|  Bandwidth wastage   | No bandwidth wastage |
|       Reserved       |     Not reserved     |
|    Constant delay    |    Variable delay    |
|      Telephone       |       Internet       |
![[Pasted image 20240422233913.png|center]]
___
#### Host attachment with a low level of effort

* Autoconfiguration
It requires several protocols to configure IP module.
DHCP, DNS/mDNS, ARP, etc.
Stateful Address Autoconfiguration (DHCPv6)
Stateless Address Autoconfiguration (SLAAC)
* No routing information at the end host
The end host just sends packets to the default router detected by autoconfiguration phase.
* 자동 구성
IP 모듈을 구성하려면 여러 프로토콜이 필요합니다.
DHCP, DNS/mDNS, ARP 등.
상태 저장 주소 자동 구성(DHCPv6)
상태 비저장 주소 자동 구성(SLAAC)
* 최종 호스트에 라우팅 정보 없음
최종 호스트는 자동 구성 단계에서 감지된 기본 라우터로 패킷을 보내기만 합니다.

> [!gpt] Autoconfiguration이 뭐야?
> Autoconfiguration은 시스템이나 장치가 자동으로 구성되는 과정을 말합니다. 이는 사용자가 수동으로 설정을 입력하지 않고도 시스템이나 장치가 필요한 구성 정보를 자동으로 획득하고 적용할 수 있도록 하는 기술입니다.
>
>Autoconfiguration은 다양한 컴퓨팅 및 네트워크 환경에서 사용됩니다. 몇 가지 예시는 다음과 같습니다:
>
>1. **네트워크 자동 구성**: 네트워크 장치가 IP 주소, 서브넷 마스크, 게이트웨이 등의 네트워크 구성 정보를 자동으로 획득하는 것을 포함합니다. DHCP(Dynamic Host Configuration Protocol)를 사용하여 클라이언트 장치가 네트워크 구성 정보를 자동으로 가져올 수 있습니다.
>
>2. **프린터 및 네트워크 장치 구성**: 프린터나 라우터와 같은 네트워크 장치가 자동으로 네트워크 설정을 가져오고 구성할 수 있습니다. 이를 통해 사용자는 수동으로 IP 주소나 포트 설정을 입력할 필요가 없습니다.
>
>3. **운영 체제 및 소프트웨어 설정**: 컴퓨터 운영 체제나 소프트웨어도 자동으로 구성될 수 있습니다. 예를 들어, 운영 체제 설치 후 네트워크 구성, 사용자 계정 설정 등이 자동으로 수행될 수 있습니다.
>
>Autoconfiguration은 사용자의 편의성을 높이고 시스템 구성의 일관성을 유지하는 데 도움이 됩니다. 또한 오류 가능성을 줄이고 시스템 관리를 간소화하는 데 기여할 수 있습니다.

> [!gpt] IP 모듈을 구성하기 위한 프로토콜에는 어떤 것들이 있어?
> IP(Internet Protocol) 모듈을 구성하기 위한 프로토콜에는 다음과 같은 것들이 있습니다:
>
>1. **IPv4 (Internet Protocol version 4)**: 현재 인터넷에서 가장 널리 사용되는 IP 버전입니다. IPv4 주소는 32비트로 표현되며, 대부분의 네트워크 기기가 IPv4를 지원합니다.
>
>2. **IPv6 (Internet Protocol version 6)**: IPv4의 주소 고갈 문제를 해결하기 위해 개발된 다음 세대의 IP 프로토콜입니다. IPv6는 128비트 주소 체계를 사용하며, 더 많은 주소 공간을 제공하여 인터넷의 확장성을 향상시킵니다.
>
>3. **ICMP (Internet Control Message Protocol)**: IP 네트워크에서 제어 및 오류 메시지를 교환하기 위한 프로토콜입니다. ICMP 메시지는 네트워크 문제 해결, 에러 보고, 패킷의 경로 찾기 등에 사용됩니다.
>
>4. **ARP (Address Resolution Protocol)**: IP 주소를 네트워크 물리적 주소(MAC 주소)로 매핑하는 데 사용되는 프로토콜입니다. ARP는 네트워크에서 호스트의 IP 주소를 알고 있을 때, 해당 IP 주소에 대응하는 MAC 주소를 찾는 데 사용됩니다.
>
>5. **DHCP (Dynamic Host Configuration Protocol)**: 네트워크에 연결된 장치에게 자동으로 IP 주소 및 네트워크 구성 정보를 할당하는 데 사용되는 프로토콜입니다. DHCP는 IP 주소 충돌을 방지하고 네트워크 관리를 간소화하는 데 도움이 됩니다.
>
>이러한 프로토콜은 IP 네트워크에서 효율적인 통신을 위해 함께 작동하여 데이터의 전송과 관리를 지원합니다.

___
#### The resources used in the Internet architecture must be accountable.

* Accounting
Billing 
* How much resource of a network is used now?
1. Simple Network Management Protocol (SNMP)
Management Information Base (MIB)
2. Network Configuration Protocol (NETCONF)
Yet Another Next Generation (YANG)


> [!gpt]
> 이 부분은 "인터넷 아키텍처에서 사용되는 자원은 책임을 져야 한다"는 규칙에 대한 구체적인 내용을 설명하는 것으로 보입니다. 여기에는 자원을 관리하고 감시하는 데 사용되는 여러 가지 기술과 프로토콜이 포함되어 있습니다:
>
>1. **Accounting (회계)**:
 >  - 인터넷 자원 사용을 추적하고 기록하여 책임을 지는 것을 의미합니다.
 >  - 주로 과금 및 비용 관리를 위해 사용됩니다.
>
>2. **Billing (과금)**:
 >  - 자원 사용에 대한 비용을 계산하고 청구하는 프로세스입니다.
 >  - 서비스 제공 업체는 사용자에게 자원 사용에 대한 비용을 청구하기 위해 과금 시스템을 운영합니다.
>
>3. **Simple Network Management Protocol (SNMP)**:
 >  - 네트워크 장치 및 시스템을 관리하기 위한 프로토콜입니다.
 >  - SNMP는 네트워크 장치의 상태 및 성능 정보를 모니터링하고, 관리자가 네트워크 리소스를 관리할 수 있도록 합니다.
>   
>4. **Management Information Base (MIB)**:
 >  - SNMP를 사용하여 수집된 정보를 저장하고 정의하는 데이터베이스입니다.
 >  - MIB는 네트워크 장치 및 시스템에 대한 정보를 계층적으로 구성하여 관리자가 쉽게 액세스할 수 있도록 합니다.
>
>5. **Network Configuration Protocol (NETCONF)**:
 >  - 네트워크 장치의 설정을 관리하기 위한 프로토콜입니다.
 >  - NETCONF를 사용하여 네트워크 장치의 설정을 변경하고 구성할 수 있으며, 이를 통해 자원의 효율적인 사용과 관리가 가능합니다.
>
>6. **Yet Another Next Generation (YANG)**:
 >  - NETCONF와 함께 사용되는 데이터 모델링 언어입니다.
  > - YANG은 네트워크 장치의 구성과 상태를 설명하고 정의하는 데 사용되며, NETCONF와 함께 자원의 구성과 관리를 위한 표준화된 방법을 제공합니다.
>
>이러한 기술과 프로토콜은 인터넷 아키텍처에서 자원의 사용과 관리를 효율적으로 추적하고 관리하기 위해 사용됩니다. 이는 자원의 효율적인 사용과 공정한 배분을 보장하여 인터넷 서비스의 안정성과 성능을 유지하는 데 중요합니다.

___
#### Internet Architecture
* Standard documents for Internet Architecture
RFC1958 (1996.06) Architectural Principles of the Internet
RFC1122 (1989.10) Requirements for Internet Hosts -- Communication Layers
RFC1812 (1995.06) Requirements for IP Version 4 Routers

* (RFC1958) Architectural Principles of the Internet (1996.06)
There is no architecture, but only a tradition, which was not written down for the first 25 years at least not by the IAB (Internet Architecture Board)
In very general terms, the Internet community believes
The goal is connectivity
The tool is the Internet Protocol
The intelligence is end to end

> [!gpt]
> 이 문서는 RFC1958에 나오는 내용으로, 인터넷의 아키텍처 원칙을 설명하고 있습니다. 이 문서는 1996년에 발표되었으며, 인터넷의 구조와 원칙을 다룹니다.
>
>1. **인터넷 아키텍처의 부재**: 이 문서는 인터넷의 초기에는 아키텍처가 아니라 전통이 존재했다고 설명합니다. 처음 25년 동안 IAB(Internet Architecture Board)가 아키텍처에 대해 문서로 작성하지 않았다는 것을 강조합니다.
>
>2. **인터넷 커뮤니티의 신념**:
>  - **목표는 연결성**: 인터넷의 목표는 다양한 시스템과 장치를 연결하여 정보를 교환하는 것입니다.
>   - **도구는 인터넷 프로토콜**: 인터넷의 동작과 통신은 인터넷 프로토콜을 기반으로 이루어집니다. 이 프로토콜은 데이터를 패킷화하고 전송하는 데 사용됩니다.
 >  - **지능은 End-to-End**: 인터넷에서 정보의 처리와 결정은 주로 끝단 시스템(End-systems)에 있어야 한다는 원칙입니다. 즉, 네트워크의 핵심 기능은 끝단 시스템에서 이루어져야 하며, 중간 시스템은 최소한의 처리만을 해야 합니다.
>
> 이 문서는 인터넷의 초기 구성과 원칙에 대한 개관을 제공하며, 인터넷의 핵심 목표와 기본 원칙에 대해 간결하게 설명합니다.

The current exponential growth of the network seems to show that connectivity is its own reward, and is more valuable than any individual application.
The key to global connectivity is the inter-networking layer (OSI ISO Network Layer (L3)).
The key to exploiting this layer over diverse hardware providing global connectivity is the "end-to-end argument".

> [!gpt]
> 이 문서는 RFC1958에 나오는 내용으로, 인터넷의 아키텍처 원칙을 설명하고 있습니다.
>
>1. **연결성의 보상**: 현재 네트워크의 기하급수적인 성장은 연결성 자체가 보상이라는 것을 보여줍니다. 즉, 네트워크가 커지면서 연결성이 증가하고, 이는 어떤 개별적인 응용보다 더 가치 있다는 것을 나타냅니다. 즉, 네트워크에 연결되는 것 자체가 가치가 있는 것입니다.
>
>2. **글로벌 연결성의 열쇠**: 전 세계적인 연결성의 핵심은 OSI ISO 네트워크 계층(레이어 3)에 있습니다. 이것은 인터넷에서 데이터를 라우팅하고 전달하는 데 사용되는 계층입니다.
>
>3. **다양한 하드웨어 상에서의 글로벌 연결성 활용**: 다양한 하드웨어 환경에서 글로벌 연결성을 제공하고 활용하는 데 있어서 끝-끝(end-to-end) 논의가 중요합니다. 즉, 다양한 네트워크 및 시스템 환경에서도 끝-끝 통신이 가능하도록 하는 것이 중요합니다. 이를 통해 네트워크의 전 세계적인 확장성과 융통성을 보장할 수 있습니다.
>
>이 문서는 인터넷의 성장과 글로벌 연결성에 대한 관점을 제시하며, 끝-끝 논의를 통한 연결성 확보의 중요성을 강조합니다. 인터넷은 연결성을 통해 가치를 창출하고, 다양한 하드웨어 환경에서도 효과적으로 동작할 수 있어야 한다는 원칙을 제시합니다.

It is generally felt that in an ideal situation there should be one, and only one, protocol at the Internet level
This allows for uniform and relatively seamless operations in a competitive, multi-vendor, multi-provider public network.
In practice, there are at least two reasons why more than one network layer protocol might be in use on the public Internet.
Firstly, there can be a need for gradual transition from one version of IP to another (Address shortage).
Secondly, fundamentally new requirements might lead to a fundamentally new protocol (Quality of Service).

> [!gpt]
> 이 문장은 RFC1958에 나오는 내용으로, 인터넷 레벨에서 하나의 프로토콜만 존재하는 것이 이상적이라고 설명하고 있습니다.
>
>1. **하나의 프로토콜을 갖는 이점**:
 >  - 하나의 프로토콜만 사용하는 것은 경쟁적인, 다중 공급업체 및 다중 공급자의 공공 네트워크에서 일관된 및 비교적 매끄러운 운영을 가능하게 합니다.
>   - 다수의 프로토콜을 사용하는 것보다 단일 프로토콜을 사용하는 것이 네트워크 운영을 간소화하고 통합성을 제공할 수 있습니다.
>
>2. **여러 프로토콜이 사용되는 경우**:
 >  - 그러나 실제로는 공개 인터넷에서 하나 이상의 네트워크 계층 프로토콜이 사용되는 경우가 있습니다.
 >  - 첫째, IP의 한 버전에서 다른 버전으로의 점진적인 전환(주소 부족)이 필요한 경우가 있습니다.
>   - 둘째, 근본적으로 새로운 요구 사항이 제시될 경우(서비스 품질)에는 새로운 프로토콜이 필요할 수 있습니다.
>
>즉, 하나의 프로토콜만 사용하는 것이 이상적이지만, 실제로는 여러 이유로 인해 하나 이상의 프로토콜이 사용될 수 있습니다. 이는 기존의 네트워크 환경을 고려하고 새로운 요구 사항을 충족시키기 위한 것입니다.

 The Internet level protocol must be independent of the hardware medium and hardware addressing.
This approach allows the Internet to exploit any new digital transmission technology of any kind, and to decouple its addressing mechanisms from the hardware.
It allows the Internet to be the easy way to interconnect fundamentally different transmission media, and to offer a single platform for a wide variety of Information Infrastructure applications and services.

> [!gpt]
> 이 문장은 RFC1958에 나오는 내용으로, 인터넷 레벨 프로토콜은 하드웨어 매체와 하드웨어 주소 지정과 독립적이어야 한다고 설명하고 있습니다.
>
>1. **하드웨어 매체와 독립적인 프로토콜**:
 >  - 인터넷 레벨 프로토콜은 전송 매체에 대해 독립적이어야 합니다. 즉, 어떤 종류의 디지털 전송 기술도 사용할 수 있어야 하며, 하드웨어 주소 지정 메커니즘과 분리되어야 합니다.
>
>2. **새로운 디지털 전송 기술 활용**:
 >  - 이 접근 방식은 인터넷이 어떠한 종류의 새로운 디지털 전송 기술도 활용할 수 있게 합니다. 따라서 인터넷은 기존의 디지털 통신 기술뿐만 아니라 새로운 기술의 도입을 적극적으로 수용할 수 있습니다.
>
>3. **주소 지정 메커니즘과 하드웨어의 분리**:
 >  - 이러한 접근 방식은 인터넷이 다양한 전송 매체를 쉽게 연결할 수 있도록 하며, 다양한 정보 인프라 응용 프로그램과 서비스에 대한 단일 플랫폼을 제공할 수 있게 합니다.
>   
>즉, 인터넷 레벨 프로토콜은 특정한 하드웨어에 종속되지 않고, 어떠한 디지털 전송 기술도 활용할 수 있으며, 주소 지정 메커니즘과 하드웨어가 분리되어야 한다는 것을 강조합니다. 이는 인터넷을 다양한 환경에서 쉽게 활용하고, 새로운 기술의 도입을 촉진하여 네트워크의 융통성과 발전을 지원합니다.

End-to-end functions can best be realized by end-to-end protocols.
The basic argument is that, as a first principle, certain required end-to-end functions can only be performed correctly by the end-systems themselves.
The function in question can completely and correctly be implemented only with the knowledge and help of the application standing at the endpoints of the communication system – from Saltzer
Providing that questioned function as a feature of the communication system itself is not possible.

> [!gpt]
> 이 문장은 네트워크에서 끝-끝(end-to-end) 기능이 최상의 결과를 얻으려면 끝-끝 프로토콜이 가장 적절하다는 것을 설명하고 있습니다.
>
>1. **끝-끝 기능과 프로토콜**:
 >  - 끝-끝 기능은 통신 시스템의 끝점에서 수행되어야 하는 기능을 말합니다. 예를 들어, 데이터의 암호화, 에러 처리, 흐름 제어 등이 해당됩니다.
>   - 이러한 끝-끝 기능은 통신 시스템의 끝점인 끝단 시스템(End-systems)에서만 정확하게 수행될 수 있습니다.
>
>2. **애플리케이션의 지식과 도움**:
 >  - 끝-끝 기능은 통신 시스템의 끝점에 위치한 애플리케이션의 지식과 도움을 필요로 합니다. 즉, 통신 시스템의 끝단에서는 통신이 정확하게 이루어질 수 있도록 애플리케이션이 참여해야 합니다.
>
>3. **통신 시스템의 기능과 애플리케이션의 분리**:
 >  - 네트워크에서 끝-끝 기능을 제공하는 것은 통신 시스템 자체의 기능으로 제공하기 어렵습니다. 이는 애플리케이션의 도움과 지식이 필요하기 때문입니다.
>
>즉, 네트워크의 끝-끝 기능은 끝단 시스템에서 애플리케이션의 도움과 지식을 바탕으로 수행되어야 하며, 이를 위해 끝-끝 프로토콜이 필요하다는 것을 강조합니다. 네트워크는 이러한 기능을 제공하기 위해 통신 시스템과 애플리케이션 사이의 협력을 가능하게 해야 합니다.

A specific case is that any network will be subject to failures of transmission at some statistically determined rate.
The best way to cope with this is to accept it, and give responsibility for the integrity of communication to the end systems.
Another specific case is end-to-end security
This principle has important consequences if we require applications to survive partial network failures.
An end-to-end protocol design should not rely on the maintenance of state inside the network.
Such state should be maintained only in the endpoints, in such a way that the state can only be destroyed when the endpoint itself breaks (known as fate-sharing).
An immediate consequence of this is that datagrams are better than classical virtual circuits.
The network’s job is to transmit datagrams as efficiently and flexibly as possible.

> [!gpt]
>이 문장은 두 가지 특정 사례를 다루고 있습니다:
>
>1. **전송 오류에 대한 대응**:
 >  - 모든 네트워크는 어떤 통계적으로 결정된 비율로 전송 오류에 영향을 받을 수 있습니다.
>   - 이러한 상황에 대처하는 가장 좋은 방법은 이를 수용하고, 통신의 무결성을 끝단 시스템에게 맡는 것입니다.
 >  - 즉, 전송 오류가 발생할 수 있음을 인정하고, 통신의 무결성을 보장하기 위한 책임은 통신의 끝단에게 있어야 한다는 것입니다.
>
>2. **끝-끝 보안**:
 >  - 또 다른 특정 사례는 끝-끝 보안입니다.
 >  - 이 원칙은 특히 네트워크의 일부분이 실패할 경우 애플리케이션의 작동을 보장해야 할 때 중요한 영향을 미칩니다.
>   - 끝-끝 프로토콜 디자인은 네트워크 내부의 상태 유지에 의존해서는 안 됩니다. 이러한 상태는 끝점에서만 유지되어야 하며, 끝점이 고장날 때만 상태가 소멸되어야 합니다(운명 공유).
 >  - 이러한 원칙에 따라 데이터그램은 클래식 가상 회선보다 우수하다는 것이 바로 그 결과입니다. 네트워크의 역할은 데이터그램을 가능한 효율적으로 유연하게 전송하는 것입니다.
>
>이러한 원칙은 네트워크 디자인에서 끝-끝 프로토콜의 중요성과 효과를 강조하며, 네트워크의 역할과 책임을 명확히 합니다. 끝-끝 원칙은 통신의 무결성과 보안을 보장하고, 데이터의 유연하고 효율적인 전송을 위해 중요한 원칙으로 작용합니다.

* Components of the Internet Architecture (Host and Router) and Architecture Assumptions
(RFC 1122) Requirements for Internet Hosts -- Communication Layers (1989.10)
(RFC 1123) Requirements for Internet Hosts -- Application and Support
(RFC 1812) Requirements for IP Version 4 Routers (1995.06)

* (RFC 1122) Requirements for Internet Hosts -- Communication Layers (1989.10)
-The Internet Components 
A host computer, or simply "host," is the ultimate consumer of communication services
An Internet communication system consists of interconnected packet networks supporting communication among host computers using the Internet protocols
The networks are interconnected using packet-switching computers called "gateways" or "IP routers" by the Internet community
-Architectural Assumptions
The Internet is a network of networks.
Gateways do not keep connection state information.
Routing complexity should be in the gateways
The system must tolerate wide network variation.

> [!gpt]
> 이 문서는 RFC 1122에 나오는 내용으로, 인터넷 호스트의 통신 계층에 대한 요구 사항과 인터넷의 구성 요소, 아키텍처적 가정 등에 대해 설명하고 있습니다.
>
>1. **인터넷 구성 요소**:
 >  - 호스트 컴퓨터, 또는 간단히 "호스트"는 통신 서비스의 최종 소비자입니다.
 >  - 인터넷 통신 시스템은 인터넷 프로토콜을 사용하여 호스트 컴퓨터 간의 통신을 지원하는 상호 연결된 패킷 네트워크로 구성됩니다.
>   - 네트워크는 인터넷 커뮤니티에 의해 "게이트웨이" 또는 "IP 라우터"라고 불리는 패킷 스위칭 컴퓨터를 사용하여 상호 연결됩니다.
>
>2. **아키텍처적 가정**:
 >  - 인터넷은 네트워크의 네트워크입니다. 즉, 다양한 네트워크가 상호 연결되어 하나의 큰 네트워크를 형성합니다.
 >  - 게이트웨이는 연결 상태 정보를 유지하지 않습니다. 즉, 연결 상태 정보는 끝-끝 시스템에 의해 유지되어야 합니다.
 >  - 라우팅 복잡성은 게이트웨이에 있어야 합니다. 즉, 네트워크 라우팅 결정은 게이트웨이에 의해 수행되어야 하며, 라우팅 결정의 복잡성은 게이트웨이에게 위임되어야 합니다.
 >  - 시스템은 넓은 네트워크 변동을 용인해야 합니다. 즉, 네트워크의 다양성과 변화에 대응할 수 있는 유연성을 가져야 합니다.
>
>이 문서는 인터넷 호스트와 인터넷의 구성 요소에 대한 설명과 함께, 인터넷 아키텍처의 가정과 요구 사항에 대해 설명하고 있습니다. 이러한 가정과 요구 사항은 인터넷의 설계와 운영을 지원하는 데 중요한 역할을 합니다.

* (RFC1812) Requirements for IP Version 4 Routers (1995.06)
-Internet Data Units
--Link Layer
---Frame (LL header + IP Packet)
--IP Layer
---Packet 
----A datagram
----Fragments of a datagram
---Datagram
----IP header + (Msg or Seg)
--Transport Layer
---Message (UDP)
---Segment (TCP)
--Application
---Record
---Byte Stream

> [!gpt]
> 이 문서는 RFC 1812에 나오는 내용으로, IPv4 라우터에 대한 요구 사항에 대해 설명하고 있습니다. 여기서는 인터넷 데이터 유닛(인터넷에서 데이터를 전송하는 데 사용되는 단위)에 대한 구성과 계층적 구조를 설명하고 있습니다.
>
>1. **인터넷 데이터 유닛**:
 >  - 인터넷에서 데이터를 전송할 때 사용되는 데이터의 단위를 설명합니다.
>  
>2. **링크 계층**:
 >  - 링크 계층에서는 데이터를 프레임으로 전송합니다. 프레임은 링크 계층 헤더와 IP 패킷으로 구성됩니다.
>
>3. **IP 계층**:
 >  - IP 계층에서는 데이터를 패킷 또는 데이터그램으로 전송합니다. 패킷은 데이터그램의 한 형태이며, 데이터그램은 IP 헤더와 메시지 또는 세그먼트로 구성됩니다. 또한 데이터그램은 하나의 완전한 메시지 또는 데이터를 나타내거나, 데이터그램의 일부인 분할된 데이터를 나타낼 수 있습니다.
>
>4. **전송 계층**:
>   - 전송 계층에서는 데이터를 메시지(UDP) 또는 세그먼트(TCP)로 전송합니다.
>
>5. **응용 계층**:
 >  - 응용 계층에서는 데이터를 레코드 또는 바이트 스트림으로 전송합니다.
>
>이러한 계층적 구조는 데이터를 효율적으로 전송하고 처리하기 위해 다양한 단계로 나누어진 것을 나타냅니다. 각 계층은 특정한 역할과 책임을 가지고 있으며, 데이터의 전송과 처리를 위해 상호작용합니다.

![[Pasted image 20240423010423.png|center]]
