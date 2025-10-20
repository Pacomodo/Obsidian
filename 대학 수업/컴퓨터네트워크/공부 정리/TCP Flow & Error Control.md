
> [!gpt] TCP Flow Control과 Error Control에 대해 간략하게 설명해줘
> TCP Flow Control은 데이터 전송 시 송신자와 수신자 간의 데이터 흐름을 조절하는 메커니즘입니다. 송신자는 네트워크 상황을 고려하여 수신자가 처리할 수 있는 만큼의 데이터만을 전송하고, 수신자는 이를 받아들여 처리합니다. 이를 통해 네트워크 혼잡을 방지하고 데이터 전송의 신뢰성을 유지합니다.
>
>Error Control은 데이터 전송 중에 발생할 수 있는 오류를 감지하고 복구하는 메커니즘입니다. TCP는 전송되는 데이터에 대한 확인 응답 및 재전송 메커니즘을 통해 오류를 감지하고 복구합니다. 송신자는 데이터를 전송한 후 확인 응답을 기다리며, 수신자는 데이터를 받은 후 정상적으로 처리되었음을 확인하는 응답을 송신자에게 전송합니다. 송신자가 확인 응답을 받지 못하면 데이터를 다시 전송하여 오류를 복구합니다.
>
>요약하면, TCP Flow Control은 데이터 전송 속도를 조절하여 네트워크 혼잡을 방지하고 신뢰성을 유지하는 메커니즘입니다. Error Control은 데이터 전송 중 발생하는 오류를 감지하고 복구하는 메커니즘입니다. 두 가지 기능은 함께 동작하여 안정적인 데이터 전송을 보장합니다.
#### TCP Flow Control
* Purpose
	* It prevents the overflow on the receiver side
	* Method - Sliding Window
	* Related TCP Header Fields
		* Sequence Number
		* Acknowledge Number
		* Window size

> [!gpt] TCP Flow Control을 하는 방법 중 하나인 stop and wait에 대해 알려줘
> TCP Flow Control에서 "stop-and-wait" 방식은 간단한 형태의 흐름 제어 메커니즘 중 하나입니다. 이 방식은 데이터를 보낸 후 수신자로부터 확인(ACK) 응답을 받을 때까지 기다리는 방식으로 동작합니다. 데이터를 전송하고 나서 ACK를 받을 때까지 송신자는 다음 데이터를 보내지 않고 기다립니다. 이 방식은 송신자와 수신자 간의 데이터 전송 속도를 조절하여 Flow Control을 달성합니다.
>
>stop-and-wait 방식의 동작은 다음과 같습니다:
>
>1. 송신자는 데이터를 보내고 데이터의 전송이 완료되었다는 확인을 기다립니다.
>2. 수신자는 데이터를 받고 처리한 후, 받은 데이터에 대한 확인(ACK) 응답을 송신자에게 전송합니다.
>3. 송신자는 ACK를 받으면 다음 데이터를 보내는 것을 시작합니다.
>4. 이 과정을 반복하여 데이터의 전송과 확인이 순차적으로 이루어집니다.
>
>stop-and-wait 방식은 간단하고 신뢰성이 있으나, 데이터 전송의 효율성이 낮고 네트워크의 대기 시간을 증가시킬 수 있습니다. 따라서 이 방식은 네트워크 지연이 적거나 송신자와 수신자 간의 네트워크 대역폭이 비슷한 경우에 적합합니다. 더 나은 효율성을 위해서는 다른 Flow Control 메커니즘인 "sliding window"과 같은 방법을 고려할 수 있습니다.

> [!gpt] Flow Control을 하는 방법인 Sliding Window에 대해 설명해줘.
> Sliding Window는 TCP Flow Control을 위한 메커니즘 중 하나로, 송신자와 수신자 간의 데이터 전송 속도를 조절하는 방법입니다. 이 메커니즘은 송신자가 연속적으로 여러 개의 패킷을 전송하고, 수신자는 이러한 패킷을 수신하고 처리한 후 일정 크기의 윈도우 내에서 수신 확인 응답을 송신자에게 보냅니다.
>
>Sliding Window에서 윈도우는 송신자가 보낼 수 있는 패킷의 최대 개수를 나타냅니다. 수신자는 윈도우 크기 내에서 패킷을 수신하고 처리한 후 해당 패킷에 대한 확인 응답을 송신자에게 전송합니다. 송신자는 이 확인 응답을 받으면 윈도우를 이동시켜 다음 패킷을 전송할 수 있습니다. 이 과정에서 윈도우의 크기는 동적으로 조절될 수 있으며, 네트워크 상황에 따라 윈도우의 크기가 변경됩니다.
>
>Sliding Window를 사용하면 송신자와 수신자 간의 데이터 흐름을 효율적으로 조절할 수 있습니다. 송신자는 네트워크 상황에 따라 적절한 속도로 데이터를 전송하고, 수신자는 자신의 처리 속도에 맞게 데이터를 수신하고 처리할 수 있습니다. 이를 통해 네트워크 혼잡을 방지하고 데이터 전송의 신뢰성을 유지할 수 있습니다.

> [!gpt] TCP Flow Control을 하는데 관련된 TCP Header Field는 뭐야
> TCP 헤더에는 TCP Flow Control을 조절하는 데 관련된 여러 가지 필드가 있습니다. 주요한 TCP 헤더 필드 중 Flow Control과 관련된 것은 다음과 같습니다:
>
>1. **Window Size (윈도우 크기)**: TCP 헤더의 Window Size 필드는 수신자가 현재 처리할 수 있는 데이터의 양을 나타냅니다. 이 값은 수신자가 송신자에게 보낼 수 있는 최대 데이터 양을 나타내며, TCP Flow Control을 조절하는 데 중요한 역할을 합니다.
>
>2. **Acknowledgment Number (확인 응답 번호)**: TCP 헤더의 Acknowledgment Number 필드는 수신자가 마지막으로 정상적으로 수신했던 데이터의 시퀀스 번호를 나타냅니다. 이를 통해 송신자는 수신자가 얼마나 많은 데이터를 성공적으로 받았는지를 알 수 있으며, 이 정보를 기반으로 Flow Control을 수행합니다.
>
>이 외에도 TCP 헤더에는 여러 가지 다른 필드가 있으며, 이들은 TCP의 다양한 기능과 동작을 지원합니다. Flow Control과 관련된 TCP 헤더 필드는 주로 Window Size와 Acknowledgment Number입니다.

* Sliding Window
	* A sender can send data in the window without another ACK from the receiver
	* A receiver indicate the starting point of the window and its size to the sender by sending ACK-set TCP Segment
		* The starting point == Acknowledgement Number in the TCP Header
		* Its size == Window size in the TCP Header
![[Pasted image 20240430133709.png|center|500]]
![[Pasted image 20240430133723.png|center|500]]
![[Pasted image 20240430133749.png|center|600]]
1. 수신자가 잘 수신 받은 부분.
2. 송신은 했지만 수신받지 않은 부분
3. 보내지 않은 부분
4. 윈도우 바깥 부분
* Sliding Window (Sender-side)
	– SND.UNA is set to the Acknowledgement number in the header of a TCP Segment sent by the peer
	– SND.NXT is set to the next sequence number to be sent by me
	(In the example, Sequence number + data size)
	– SND.WND is set to the Window size in the header of a TCP Segment sent by the peer
	![[Pasted image 20240430134043.png|center|500]]
* Sliding Window (Receiver-side)
![[Pasted image 20240430134218.png|center|600]]
– RCV.NXT is set to the sequence number + data size if there is no error
– RCV.WND is set to the currently available buffer size
– The Window on the Receiver Buffer slides when the enqueued data is dequeued
![[Pasted image 20240430134522.png|center|600]]

> [!gpt]
> Sliding window를 사용한 TCP Flow Control은 송신자와 수신자 간의 데이터 전송 속도를 조절하는 메커니즘입니다. 이 방식은 송신자가 연속적으로 여러 개의 패킷을 전송하고, 수신자는 이러한 패킷을 수신하고 처리한 후 일정 범위의 윈도우 내에서 수신 확인 응답을 송신자에게 보냅니다.
>
>Send Sequence Space와 Receive Sequence Space는 이러한 sliding window 메커니즘에서 중요한 개념입니다. Send Sequence Space는 송신자가 보낸 데이터의 시퀀스 번호 범위를 나타내며, Receive Sequence Space는 수신자가 받을 수 있는 데이터의 시퀀스 번호 범위를 나타냅니다.
>
>동작 방식은 다음과 같습니다:
>
>1. **Send Sequence Space**: 송신자는 Send Sequence Space를 사용하여 보낸 데이터의 시퀀스 번호를 추적합니다. 송신자는 윈도우 크기 내의 다음 시퀀스 번호의 데이터를 전송할 수 있습니다. 예를 들어, 현재 윈도우의 시작 시퀀스 번호가 100이고 윈도우 크기가 10이면, 송신자는 시퀀스 번호가 110부터 119까지의 데이터를 전송할 수 있습니다.
>
>2. **Receive Sequence Space**: 수신자는 Receive Sequence Space를 사용하여 받을 수 있는 데이터의 시퀀스 번호 범위를 추적합니다. 수신자는 윈도우 내의 시퀀스 번호 범위 내의 데이터만을 수신하고 처리합니다. 예를 들어, 현재 윈도우의 시작 시퀀스 번호가 200이고 윈도우 크기가 15이면, 수신자는 시퀀스 번호가 200부터 214까지의 데이터를 수신하고 처리할 수 있습니다.
>
>3. **Acknowledgment (ACK) 메시지**: 수신자는 수신한 데이터를 처리한 후 윈도우 내의 마지막 시퀀스 번호를 포함하는 ACK 메시지를 송신자에게 전송합니다. 이 ACK 메시지는 송신자에게 현재까지 정상적으로 수신된 데이터의 시퀀스 번호를 알려주며, 송신자는 이를 기반으로 윈도우를 이동시킵니다.
>
>이와 같이 Send Sequence Space와 Receive Sequence Space를 사용하여 sliding window 메커니즘은 송신자와 수신자 간의 데이터 전송 속도를 효율적으로 조절합니다. 이를 통해 네트워크 혼잡을 방지하고 데이터 전송의 신뢰성을 유지할 수 있습니다.

![[Pasted image 20240430134717.png|center|500]]

#### Sequence Space Management

*  The first data octet immediately following the header is the lowest numbered, and the following octest are numbered consecutively.
![[Pasted image 20240430134832.png|center|500]]
* The acknowledgement mechanism employed is cumulative.
* An acknowledgement of sequence number X indicates
	- “all octets up to but not including X have been received”.
![[Pasted image 20240430134917.png|center|500]]
* A “new” acknowledgement is one for which the ineqeuality below holds
	- SND.UNA < SEG.ACK =< SND.NXT
	- If not, it indicates some errors
![[Pasted image 20240430135008.png|center|500]]
* TCP Segment is judged to occupy “a portion of valid receive sequence space” if
	- RCV.NXT =< SEG.SEQ < RCV.NXT + RCV.WND or
	- RCV.NXT =< SEG.SEQ+SEG.LEN-1 < RCV.NXT+RCV.WND
		* SEG.SEQ == Sequence Number in the header of the received TCP segment
		* SEG.LEN == data length (not presented in header) of the received TCP segment
![[Pasted image 20240430135243.png|center|500]]
![[Pasted image 20240430135619.png|center|500]]
* A TCP receiver should not shrink the window
	– SND.UNA + SND.WND <= SEG.ACK + SEG.WND
	– Right-edge of the window cannot slide to the left
![[Pasted image 20240430135805.png|center|500]]
* When SND.NXT is over the Window, it is said "Window is zero“
	![[Pasted image 20240430135850.png|center|400]]
	- The Window can be increased by ACK from the receiver
		It means that, if ACK is not sent, the Window cannot be increased.
		ACK is generated whenever the receiver receives a TCP segment from the sender.
	![[Pasted image 20240430135935.png|center|400]]
* Solution : Zero Window Probing
	- Send a TCP segment which includes 1-byte data
	- If the receiver has more window and receives such TCP segment, it receives the data and sends an acknowledgement which contains the new Window.
	- If the receiver has no more window but receives such TCP segment, it sends an acknowledgement which contains Window 0.
	![[Pasted image 20240430140115.png|center|400]]
* Silly Window Syndrom
	- Small window size causes data to be transmitted into small segments
	- Small segments causes communication inefficiency
		- Overhead needed to send a data should be minimized
		- However, the portion of overhead (in this case, IP + TCP headers) is higher if the size of segment is small.
	![[Pasted image 20240430140238.png|center|400]]
	* However, the sending TCP packages the data to be transmitted into segments which fit the current window, and may repackage segments on the retransmission queue.
	* Solution for Silly Window Syndrom Avoidance
		* Receiver does not notify the small window size
		* Sender does not send small segments
* Receiver does not notify the small window size
	- The receiver is to keep RCV.NXT + RCV.WND fixed until the following condition satisfies:
		- RCV.NXT + RCV.WND can slide to the right with the amount of min(Fr * buffer size, Eff.snd.MSS)
		- Note that RCV.NXT + RCV.WND is the variables notified to the sender
		- Available buffer size is acquired whenever the user takes the buffered data
		- The shrink of “Range 1” occurs the extension of "Range 3"
		![[Pasted image 20240430140438.png|center|400]]
	![[Pasted image 20240430140456.png|center|400]]
	![[Pasted image 20240430140523.png|center|400]]
	![[Pasted image 20240430140546.png|center|400]]
* Sender does not send small segments
	 * If there is unacknowledged data (SND.NXT > SND.UNA), then the sending TCP buffers all data until the outstanding data has been acknowledged or until TCP can send a full-sized segment (Eff.snd.MSS)
	- It causes the sending of segments as much as big.
	- This algorithm is called "Nagle Algorithm"
	![[Pasted image 20240430140645.png|center|400]]
	![[Pasted image 20240430140703.png|center|400]]
	![[Pasted image 20240430140715.png|center|400]]
#### Delayed ACK
* A host can increase efficiency in both the Internet and the hosts by sending fewer than one ACK segment per data segment received.
	 - ACK segment which does not have any data is just overhead from the viewpoint of data transmission.
* A TCP should implement a delayed ACK, but an ACK should not be excessively delayed
	 - the delay must be less than 0.5 seconds (BSD:200ms)
		 ![[Pasted image 20240430140932.png|center|400]]
	* an ACK should be sent for at least every second segment in a stream of full-sized segments.
		![[Pasted image 20240430141000.png|center|400]]
* Delayed ACK on the receiver may occur inefficiency if the Nagle algorithm is used on the sender.
	- Nagle algorithm does not send "Not-full-sized segment“ until all the outstanding data is acknowledged.
	- Delayed ACK does not send ACK immediately until Delayed ACK timer is expired or two consecutive full-sized segments are arrived.
	- If the sender do not send two consecutive full-sized segments, the receiver sends ACK after Delayed ACK timer. Therefore, the sender waits Delayed ACK timer together to send the next segment.
	![[Pasted image 20240430141103.png|center|300]]

#### TCP Error Control
* Error
	- Lost segment
		 Detection method : Sequence number
		 Handling method : Retransmission
	- Out-of-order segment
		 Detection method : Sequence number
		 Handling method : Reordering
	- Duplicated segment
		 Detection method : Sequence number
		 Handling method : Discarding
	- Corrupted segment
		 Detection method : Checksum
		 Handling method : Retransmission
	- TCP handles the most of errors using Retransmission
* Retransmission
	- After the retransmission timeout, the sender goes back to the sequence number not acknowledged.
	![[Pasted image 20240430141255.png|center|400]]
* Fast Retransmission
	- The receiver goes back to the last sequence number where there is no error
	- The receiver requests a retransmission from the last sequence number to the sender
		* By sending ACKs
		* Such ACKs are called “Duplicate ACK“
		* It waits a small number of duplicate ACKs to be received.
			* In order to make sure a TCP segment has been lost
			* To determine whether the duplicate ACKs are generated by out-of-order or segment lost.
			* Default : 3
		*  If the configured number of duplicate ACKs are received, fast retransmission starts
![[Pasted image 20240430141442.png|center|600]]
![[Pasted image 20240430141455.png|center|600]]
* Retransmission Timeout
	- It is best if the retransmission timeout (RTO) is slightly higher than Round-trip time (RTT)
		- If lower, Retransmission timeout is expired before the ACK is arrived
		![[Pasted image 20240430141542.png|center|400]]
		* If much higher, reaction time to detect error will be late
		![[Pasted image 20240430141601.png|center|400]]
	* Calculation
		* Based on smoothed average
		* Smoothed RTT (SRTT)
			* ALPHA * SRTT + (1-ALPHA)*RTT
		* Retransmission TimeOut (RTO)
			- min(UBOUND, max(LBOUND, (BETA\*SRTT)))
			- UBOUND == an upper bound of the timeout (60 seconds)
			- LBOUND == an lower bound on the timeout (1 second)
			- ALPHA == Smooting weight
				- The higher the ALPHA is, the lower the impact of the new RTT.
				- 0.8~0.9
			* BETA == Multiplier to make the RTO slightly higher than SRTT
				* 1.3~2.0
		* Whenever a retransmission is failed, RTO for the segment increases exponentially.
			* RTO = RTO\*2
		![[Pasted image 20240430141818.png|center|400]]
* The Sample of RTT
	- It is based on the round-trip time of data segment and its related ACK.
	- However, the measurement of the RTT may be ambiguous
	![[Pasted image 20240430141924.png|center|400]]
	* To prevent this situation, TCP must use Karn’s algorithm
		* RTT samples must not be made using segments that were retransmitted.