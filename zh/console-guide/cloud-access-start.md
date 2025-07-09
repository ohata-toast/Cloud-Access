# Cloud Access 시작하기

**Security > Cloud Access > 콘솔 사용 가이드 > Cloud Access 시작하기**

<br>

## 콘솔 설정하기

에이전트 준비를 완료한 뒤 Cloud Access 서비스를 사용할 수 있도록 연결 설정을 하고 라우팅을 설정합니다.

<br>

### 설정 정보 저장

연결 설정 정보를 입력합니다. 정보를 저장한 뒤 Cloud Access를 사용할 수 있습니다.

![setting_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/setting_1.png)

* VPC와 서브넷을 선택합니다.
    * 만약, VPC와 서브넷이 없을 경우 **Network** 카테고리에서 먼저 생성하세요.
* 고객 이름을 입력합니다.
    * 한글, 영어, 숫자, 그리고 일부 기호(-, _, .)를 입력할 수 있습니다.
* 알고리즘을 선택합니다.
    * 알고리즘은 AES-256과 ChaCha20을 지원합니다.

<br>

## 라우트 설정

외부에서 에이전트를 사용해 연결된 사용자가 내부 인스턴스에 접근할 수 있도록 라우트를 설정합니다.
예를 들어, 사용자 IP 할당 대역은 10.0.0.0/24 이고 연결 설정시 선택한 서브넷은 172.16.0.0/24, 그리고 접근 가능 대역은 172.16.0.0/24일 때 VPC 라우트에 아래와 같은 룰을 추가합니다.

* 대상 CIDR: 10.0.0.0/24
* 게이트웨이: Virtual_IP 타입의 TRAFFIC_SUBNET_INTERFACE_VIP

<br>

!!! danger 주의
    * 설정 정보 저장 전 선택한 VPC에 인터넷 게이트웨이가 연결되어 있는지 확인하세요.
        * 인터넷 게이트웨이가 연결되어 있지 않으면 Cloud Access를 사용할 수 없습니다.
    * 사용자 IP 할당 대역은 아래의 항목과 겹칠 수 없습니다.
        * 연결 설정 시 선택한 서브넷
        * 접근 가능 대역 

<br>

## 에이전트 다운로드

Cloud Access 서비스 사용을 위한 에이전트를 다운로드 합니다. 서비스에서 지원하는 운영체제는 아래와 같습니다.

* Windows 10 1903 이상(32bit/64bit)
* Windows 11 (64bit)
* macOS 12.0 이상

### [Windows 다운로드(64bit)](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_6b5ee6a5d2584600b5ffd3330de1846b/windows/installer/CloudAccess_Setup_x64.exe)

### [Windows 다운로드(32bit)](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_6b5ee6a5d2584600b5ffd3330de1846b/windows/installer/CloudAccess_Setup_x86.exe)

### [macOS 다운로드](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_6b5ee6a5d2584600b5ffd3330de1846b/macos/CloudAccess%20Installer%20v0.0.1-5309-DEV.dmg)

<br>

## 연결 설정하기

### 연결 추가

에이전트를 사용하여 nhn cloud 리소스에 접속하기 위해 연결항목을 추가합니다.

![conncetion_add_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/connection_add_1.png)

➊ 도메인 주소, ➋ 고객 키, ➌ 비밀 키를 NHN Cloud 콘솔 권한을 가진 사용자에게 전달받아 입력합니다. 

<br>

![conncetion_add_3.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/connection_add_3.png)

➍ 검증 버튼을 클릭 시 검증이 완료되면 ➎ 고객 이름을 확인할 수 있고, 추가 버튼을 클릭해 연결을 추가합니다.

### 연결 삭제

연결 항목을 클릭하면 연결 삭제 버튼이 활성화 되어 추가한 연결 항목을 삭제할 수 있습니다.

<br>

!!! tip 알아두기
    * 연결 추가에 필요한 값은 NHN Cloud 콘솔 권한이 있는 사용자를 통해 확인할 수 있습니다.
        * 고객 이름은 검증이 완료되면 사용자(관리자)가 입력한 이름으로 자동으로 노출됩니다.
    * 다수의 연결항목을 추가할 수 있으나 연결은 1개만 가능합니다.

<br>

## 인증을 통한 터널 연결하기

접속이 필요한 연결을 선택한 뒤 **연결** 버튼을 클릭해 인증을 진행합니다.

### 안내 설정

* Cloud Access 서비스 권한을 가진 관리자가 설정한 안내 문구를 노출합니다.   
    * **설정-안내 설정** 사용 안 함 설정 시 노출되지 않습니다.

### 1차 인증 (계정 및 비밀번호)

![login_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/login_1.png)

* 계정명: Cloud Access 서비스 권한을 가진 관리자에게 생성받은 계정을 입력합니다.
* 비밀번호: 계정 생성 요청 시 입력한 메일주소로 수신받은 임시 비밀번호를 입력합니다.

### 개인정보 수집·이용 동의
* Cloud Access 서비스를 운영하기 위한 개인정보를 수집합니다.
    * 거절 시 서비스 이용이 제한될 수 있습니다.

### 추가 인증

* 1차 인증을 완료하게 되면 관리자가 설정한 인증 정책에 따라 추가 인증을 진행합니다. 
    * 인증 방식은 총 4개의 방식을 지원합니다.
        * 이메일
        * 휴대폰 
        * TOTP 
        * 생체 정보(패스 키) 

### 초기 비밀번호 변경

* 초기 비밀번호를 변경합니다.
    * Cloud Access 서비스 권한을 가진 관리자가 설정한 비밀번호 정책에 따라 비밀번호를 변경할 수 있습니다.

<br>

!!! tip 알아두기
    * nhn cloud 콘솔 권한을 가진 사용자(관리자)가 사용자 계정을 생성하면 등록된 사용자의 이메일 주소로 임시 비밀번호가 발송됩니다.
    * 개인정보 수집·이용 동의는 계정을 생성한 뒤 첫 인증시에만 동의를 득하며, 계정 연결이 완료되어야만 동의를 득한 것으로 간주합니다. (동의 수락을 클릭 후 인증이 완료되지 않고 취소하면 다시 동의를 해야합니다.)
    * 비밀번호 설정 시 관리자가 설정한 비밀번호 정책과 관계없이 아래의 정책은 필수로 적용됩니다.
        * 6자리 이상 30자리 이하의 길이
        * 사용자 계정(ID)과 동일한 비밀번호 설정 금지

<br>

## 에이전트 기능 살펴보기

에이전트의 트레이 아이콘 기능에 대해서 살펴봅니다.

<br>

### 에이전트 연결 전
 * 열기: 연결 항목을 보여주는 창을 엽니다.
 * 연결: 연결 항목을 보여줍니다.
 * 업데이트 확인: 에이전트의 현재 상태를 확인합니다. 업데이트 필요 시 업데이트를 진행합니다.
* 버전 정보: 에이전트의 현재 버전 정보와 오픈소스 라이선스 및 개인정보 처리 방침을 확인할 수 있습니다.
 * 설정: 에이전트의 환경 설정 및 언어 설정을 할 수 있습니다.
      * 클라우드 환경 설정: 민간 또는 공공클라우드를 설정합니다.
      * 언어 설정: 한국어, 영어, 일본어를 지원합니다.
 * 종료: 에이전트를 종료합니다.

### 에이전트 연결 후
* 고객이름과 계정 이름이 노출됩니다.
* 열기: 연결 항목을 보여주는 창을 노출합니다.
* 연결 해제: 에이전트 연결을 해제합니다.
* 공지: 설정된 공지를 확인합니다. (공지가 설정되어 있지 않을 수 있습니다.)
* 버전 정보: 에이전트의 현재 버전 정보와 오픈소스 라이선스 및 개인정보 처리 방침을 확인할 수 있습니다.
* 종료: 에이전트를 종료합니다.
