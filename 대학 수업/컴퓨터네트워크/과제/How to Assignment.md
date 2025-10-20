1. VM1을 실행시킨다.
2. VM2를 실행시킨다.
3. 두 VM모두 터미널 실행시킨다.
4. VM1에 대해서 다음 명령어를 실행시킨다.
5. sudo su
6. 암호 입력
7. echo reno > /proc/sys/net/ipv4/tcp_congestion_control
8. VM2에 대해서 5~7 실행
9. VM1에 대해서 다음 명령어 실행
10. ethtool -K enp0s3 tso off
11. ethtool -K enp0s3 gro off
12. VM2에 대해서 10~11 실행
13. VM1, VM2 모두 터미널을 닫아준다.
___
1. VM1에 대해서 다음 실행
2. sudo ip route change 10.1.1.0/24 dev enp0s3 proto static initcwnd 1
3. 암호 입력
4. sudo mount -t vboxsf CN_share share
5. cd ./share
6. VM2에 대해서 4~5 실행
7. VM2에 빈 터미널 하나 더 실행
8. sudo wireshark
9. enp0s3로 들어가기
10. 이후 다른 터미널에서 ./tcp_server
11. VM1에서는 ./tcp_client
12. VM2의 결과 나오면 멈추고 저장.
13. ctrl+C로 종료(VM2)
























