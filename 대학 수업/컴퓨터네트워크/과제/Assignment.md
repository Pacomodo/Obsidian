___
1. TCP 3-way handshake
___
![[Pasted image 20240528131505.png|center|400]]
첫번째 SYN 패킷을 분석하면 다음과 같다. SYN flag가 켜진 것은 다음과 같이 확인할 수 있다.
___
![[Pasted image 20240528124017.png|center|400]]
Initial Sequence Number(ISN)은 송신자인 VM1(10.1.1.1)이 설정을 한다.
이때 클럭 기반으로 설정이 되었고, 8a9b9ec6(**2325454534**)로 ISN을 설정했다.
___
![[Pasted image 20240528134524.png|center|500]]
더불어, TCP Option들은 다음과 같이 설정되어있는데, 이는 VM1이 한 번에 최대 1460바이트의 세그먼트를 수신할 수 있다는 사실을 VM2에게 알리는 것이다. 또한, 윈도우 스케일이 7로 설정이 되었음을 확인할 수 있다.
___
![[Pasted image 20240528140238.png|center|500]]
두번째 패킷이 SYN+ACK 패킷이라는것은 다음 플래그를 통해 확인할 수 있다.
___
![[Pasted image 20240528124655.png|center|500]]
두번째 SYN+ACK 패킷을 보면, 첫번째 패킷을 수신자(VM2)가 잘 받았으므로, 이에 대한 응답으로, 앞으로 송신자(VM1)에게 기대할 Sequence number, 즉, VM1의 ISN보다 하나가 더 큰 2325454534 + 1 = **2325454535**로 Acknowledge number를 설정하고 있음을 확인할 수 있다. 더불어, 송신자인 VM2(10.1.1.2)가 설정한 ISN은 cc7904d5(**3430483157**)임을 확인할 수 있다.
___
![[Pasted image 20240528140545.png|center|500]]
더불어, TCP Option들은 다음과 같이 설정되어있는데, 이는 VM2이 한 번에 최대 1460바이트의 세그먼트를 수신할 수 있다는 사실을 VM1에게 알리는 것이다. 또한, 윈도우 스케일이 7로 설정이 되었음을 확인할 수 있다.
두 MSS가 서로 일치하므로, 가장 효율적인 송신 MSS(Eff.snd.MSS)는 두 MSS의 Minimum값인 1460바이트가 될 것임을 알 수 있다.
___
![[Pasted image 20240528141235.png|center|500]]
세번째 패킷은 ACK 패킷임을 다음 플래그를 통해 확인할 수 있다.
___
![[Pasted image 20240528125541.png|center|500]]
세번째 ACK 패킷을 보면, 세번째 패킷의 송신자인 VM1(10.1.1.1)이 세번째 패킷의 수신자인 VM2(10.1.1.2)에게, VM2가 VM1에게 보냈던 패킷(SYN+ACK)을 잘 받았다는 응답을 하고 있다. 이에 대한 것으로, 앞으로 기대할 Sequence Number, 즉, VM2의 ISN보다 하나 더 큰 **3430483158**을 Acknowledge number로 설정했음을 확인할 수 있다. 더불어, 이 세번째 ACK 패킷은 VM1이 보내는 두 번째 패킷이므로, relative sequence number가 1임을 확인할 수 있다.
___
2. Congestion Control 
___
Initcwnd = 1인 경우는 다음과 같다.
![[Pasted image 20240528143929.png]]
Initcwnd가 1로 설정되어있기 때문에 처음에 한 번에 보낼 수 있는 Segment 개수가 하나로 제한되어있다. 이후 ACK를 받을 때 마다, Slow start method에 의해 ACK를 받은 packet하나 당 Congestion window를 하나 씩 늘린다.
이를 8~9번 패킷, 10~13번 패킷, 14~21번 패킷을 통해 확인할 수 있다.

초기 Congestion Window (Initcwnd)가 5인 경우는 다음과 같다.
![[Pasted image 20240528150115.png]]
Initcwnd가 1인 경우와는 다르게 처음부터 한 번에 보내는 Segment의 양이 많음을 확인할 수 있다.
___
