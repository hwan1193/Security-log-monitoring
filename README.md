# Security-log-monitoring-Automation
Security Log Monitoring &amp; Alert Automation

PowerShell 기반 서버 보안 로그 감시 및 취약점 탐지 자동화 스크립트이다. (Apache, Java, Oracle 등)
운영 환경에서 주기적으로 실행되어 보안 위협 및 이상 트래픽을 탐지하고,
Teams/Slack Webhook으로 자동 알림을 전송한다.

---

## 요구사항
- Windows Server (PowerShell 접근 가능한 환경)
- PowerShell 5.1 이상 (PowerShell 7 권장)
- 대상 서버에 PSRemoting(WinRM) 활성화 시 다중 서버 원격 실행 가능
- 내부 검사 (클래스 파일 열람)를 위해 Canary에 7-zip 설치 권장
  설치 예시 : choco install 7zip -y (chocolatey 필요)

---

## 설치 및 준비
1. Canary VM 스크립트 복사.
2. 7-zip 필요 시 설치
3. 운영팀 권한으로 원격 배포/실행 권한 확보.

---

### 사용법 요약
관리자 권한으로 PowerShell에서 실행.

---

## 사용 예시

``` powershell
# Log4j & Java 탐지
.\Detect-Log4j-And-Java.ps1 -ScanPath "C:\inetpub\wwwroot" -OutFile "log4j_scan_$(Get-Date -Format yyyyMMdd).csv"

