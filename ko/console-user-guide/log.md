# 로그

**Security > Cloud Access > 콘솔 사용 가이드 > 로그**

**로그** 탭에서는 Cloud Access 서비스를 운영하면서 발생하는 여러가지 로그를 실시간으로 검색할 수 있습니다.

<br>

## 트래픽

![traffic_log.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/traffic_log.png)

사용자가 에이전트를 연결하여 Cloud Access 서비스를 통해 인스턴스를 접속할 때 발생되는 통신 트래픽 로그를 검색할 수 있습니다.
* 조회는 1개월씩 최대 3개월까지의 과거 데이터만 검색 가능합니다.

<br>

## Audit

![audit_log.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/audit_log.png)

사용자 정책 생성 및 삭제 등 Cloud Access 서비스의 변경사항에 대한 로그를 검색할 수 있습니다.
* 조회는 최대 1개월 단위로 검색 가능하며, 조직 서비스인 CloudTrail에서도 검색 가능합니다.

<br>

## 사용자

![audit_log.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/user_log.png)

사용자가 에이전트 로그인 후 Cloud Access를 사용하는 동안 에이전트에서 발생되는 모든 로그를 검색할 수 있습니다.

<br>

## 엑셀 내려받기

로그를 검색한 결과를 엑셀로 내려받을 수 있습니다.

<br>

!!! tip "알아두기"

    * 트래픽 로그는 최대 7일 또는 50,000건까지 보관하며, 둘중 하나의 조건이 중촉되면 가장 오래된 로그부터 순차적으로 삭제(덮어쓰기) 됩니다.
        * 별도의 데이터 저장이 필요한 경우 **설정** 탭의 **로그 원격전송 설정** 사용을 권장합니다.
