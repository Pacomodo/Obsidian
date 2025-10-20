#### IPv4 Forwarding Procedure

> [!gpt]
> IPv4 전달 절차는 라우터나 다른 네트워크 장비가 수신한 IPv4 패킷을 올바른 방향으로 전달하는 과정을 말합니다. 이 과정은 네트워크 계층에서 이뤄지며, 다음과 같은 단계로 구성됩니다:
>
>1. **도착 패킷 검사**: 라우터가 패킷을 수신하면 먼저 패킷의 헤더를 검사합니다. 이 과정에서는 목적지 IP 주소를 확인하고 라우터가 해당 패킷을 전달해야 하는지 결정합니다.
>
>2. **라우팅 테이블 검색**: 라우터는 목적지 IP 주소를 기반으로 라우팅 테이블을 검색합니다. 라우팅 테이블은 네트워크의 다양한 서브넷과 라우팅 정보를 포함하고 있으며, 목적지 IP 주소에 따라 패킷을 올바른 인터페이스로 전달할 수 있는 경로를 결정합니다.
>
>3. **패킷 전달**: 라우터는 라우팅 테이블에서 얻은 정보를 기반으로 패킷을 올바른 인터페이스로 전달합니다. 이 과정에서는 MAC 주소를 결정하고 패킷을 해당 인터페이스로 보냅니다.
>
>4. **전송**: 패킷이 올바른 인터페이스로 전달되면, 해당 인터페이스를 통해 네트워크로 패킷이 전송됩니다. 이때 패킷은 해당 네트워크의 물리적인 주소(MAC 주소)를 사용하여 목적지로 전송됩니다.
>
>5. **다음 라우터로 전달**: 경우에 따라 목적지가 현재 라우터에 직접 연결되어 있지 않은 경우, 패킷은 다음 라우터로 전달됩니다. 이 과정은 위의 단계를 반복하여 목적지에 도달할 때까지 계속됩니다.
>
>IPv4 전달 절차는 네트워크의 효율적인 동작을 보장하기 위해 중요합니다. 이를 통해 라우터는 패킷을 최적의 경로로 전달하여 네트워크 전체의 성능을 향상시킬 수 있습니다.

* IPv4 addresses are assigned to an interface, while the assigned IPv4 addresses can identify “host” where the interface is equipped
![[Pasted image 20240423062950.png|center|500]]
* By the routing function, the routing entry to be used is selected.
* How to use the routing entry?
	Look the interface # and the next-hop IPv4 address
	Forward the IPv4 packet to the next-hop, using lower layers
		Destination lower layer identifier (for the next-hop) is required
* Direct Forwarding
	Next-hop is ::
	It indicates that the next-hop IPv4 address is same as “the destination IPv4 address”
* Indirect Forwarding
	Next-hop is specified
