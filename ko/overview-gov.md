# Cloud Access 개요

**Security > Cloud Access > 개요**

Cloud Access는 제로 트러스트 보안 모델을 기반으로 NHN Cloud 리소스에 안전하게 접속할 수 있도록 지원하는 서비스입니다.

전용 에이전트를 통해 사용자는 복잡한 설정 없이 손쉽게 리소스에 접근할 수 있으며, 관리자는 NHN Cloud 콘솔에서 사용자 및 지속 인증, 실시간 로깅 및 모니터링 기능을 활용해 효율적으로 서비스를 운영할 수 있습니다.

<br>

## 주요 기능

* 맞춤형 계정 관리
    * 관리자는 각 사용자에게 맞춤형 접속 권한과 정책을 적용할 수 있습니다. 단순한 허용/차단을 넘어서 사용자가 어떤 리소스에, 어느 시간대에, 어떤 디바이스를 사용하여 접근 가능한지를 상세하게 제어할 수 있습니다.
    * 사용자를 고객 환경에 맞게 그룹화하여 정책을 일괄 적용할 수 있으므로 복잡한 사용자 환경에서도 일관성 있는 보안 정책 운영이 가능합니다.
* 지속적인 디바이스 검증
    * 설정된 정책에 따라 사용자가 리소스에 접속할 때 사용하는 디바이스의 IP/MAC, OS, 프로세스, 레지스트리, 백신 등을 지속적으로 검증하며, 정책 위반 시 재인증을 요구합니다.
* 실시간 모니터링 및 로깅
    * 사용자의 접속 시도, 인증 이력, 정책 위반 등 다양한 사용자의 활동을 실시간으로 수집하고 저장합니다.
        * 관리자는 현재 누가 어디에 접속 중인지, 어떤 이상 징후가 발생했는지 등 사용자의 상세 정보를 빠르게 파악할 수 있습니다.
    * 수집된 로그는 고객의 보안 요건에 맞춰 NHN Cloud의 Object Storage(OBS) 또는 Log & Crash Search 서비스와 연동해 자동으로 적재됩니다. 이를 통해 장기적인 로그 보관과 규제 준수를 위한 감사 대응이 가능하며, 고객은 보다 체계적인 보안 운영 환경을 구축할 수 있습니다.

<br>

  ## 구성

  Cloud Access는 아래와 같이 구성할 수 있습니다.

  ![conncetion_Architecture_1.PNG](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_cloud_access/2025.06.24/2025.07/Architecture_1.png)

* 접속이 필요한 인스턴스가 속한 VPC에서 Cloud Access 전용 서브넷을 생성합니다.
* 생성한 서브넷을 사용하여 Cloud Access를 생성합니다.

!!! tip "알아두기"

    * Cloud Access는 여러 가지 방식으로 구성할 수 있습니다. 자세한 설정 방법은 [콘솔 사용 가이드 - 시작하기](https://docs.gov-nhncloud.com/ko/Security/Cloud%20Access/ko/console-user-guide/cloud-access-start/)를 참고하세요.