# system-optimizer
system optimizer
네트워크 연결 최적화\
#!/bin/bash

# 불필요한 네트워크 서비스 중지
sudo systemctl stop bluetooth.service
sudo systemctl disable bluetooth.service
sudo systemctl stop avahi-daemon.service
sudo systemctl disable avahi-daemon.service

# 네트워크 프로토콜 설정 최적화
sudo sysctl -w net.ipv4.tcp_window_scaling=1
sudo sysctl -w net.ipv4.tcp_timestamps=1
sudo sysctl -w net.ipv4.tcp_sack=1

echo "네트워크 연결 최적화가 완료되었습니다."

시스템 부팅속도 개선
#!/bin/bash

# 불필요한 부팅 서비스 제거
sudo systemctl disable ModemManager.service
sudo systemctl disable cups.service
sudo systemctl disable plymouth-quit-wait.service

# 마이크로 최적화
sudo systemd-analyze critical-chain
sudo systemd-analyze verify

echo "시스템 부팅 속도 개선이 완료되었습니다."


