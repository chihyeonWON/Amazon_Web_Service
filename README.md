![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/2bf3d35a-b9a2-41f5-bbd5-43acf7ec6da4)
```
최근 대학쪽에서 AWS교육 관련 수요 or 정부과정 협업 요청이 늘고 있습니다.

아래 AWS 전체 교육 프로그램 확인해보시고 문의사항이 있으면 언제든지 연락주세요.

 

AWS 교육 통합 프로그램 제안 :

https://jaeman.awsapps.com/workdocs/index.html#/share/document/0322a0d99cba2b790a0037f382b5919aeeded29da1c5a241c604cb7c4a1d5dfc
 

AWS교육프로그램 취업사례 영상 :

IBM:
https://jaeman.awsapps.com/workdocs/index.html#/share/document/2e740bb0eaa265e3edce4169f1b67c69cacabed9b9c46fea97bce5330bfe1258

디지베이스(AWS 파트너사):
https://jaeman.awsapps.com/workdocs/index.html#/share/document/95aa82fe88e22efb9564c2fae79df9a2ba31f15cd90c8102132b27856dc33a75

에티버스(구 영우클라우드 - AWS 파트너사):
https://jaeman.awsapps.com/workdocs/index.html#/share/document/c6b8c91d5c9a8fff9a70e11e69aea232e8f5847ff843224dfdf1926479fceb38

 

감사합니다

박재만드림

Jaeman Park

Senior Program Manager

AWS Skills to Jobs KR & JP

Amazon Web Services

+82-1047010153

parkjaem@amazon.com

AWS Educate | AWS Academy

 

signature_513042695
```

## 실습 2: VPC 구축 및 웹 서버 시작
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/1b7a8ccd-2be1-424e-a165-b419a6893fcf)
```
버전 4.6.6(TESS1)

이 실습에서는 Amazon Virtual Private Cloud(VPC)를 사용하여 자체 VPC를 생성하고 구성 요소를 추가하여 사용자 지정된 네트워크를 생성합니다. 또한 EC2 인스턴스에 대한 보안 그룹을 생성합니다. 그런 다음 웹 서버를 실행하고 VPC에서 시작하도록 EC2 인스턴스를 구성하고 사용자 지정합니다.

Amazon Virtual Private Cloud(Amazon VPC)를 사용하면 사용자가 정의한 가상 네트워크에서 AWS(Amazon Web Services) 리소스를 시작할 수 있습니다. 이 가상 네트워크는 고객의 자체 데이터 센터에서 운영하는 기존 네트워크와 매우 유사하며, AWS의 확장 가능한 인프라를 사용한다는 이점이 있습니다. 여러 가용 영역에 걸쳐 있는 VPC를 생성할 수 있습니다.
목표

본 실습을 완료하면 다음을 할 수 있습니다.

VPC 생성.
서브넷 생성.
보안 그룹 구성.
VPC에서 EC2 인스턴스 시작.
 

소요 시간

이 실습은 완료까지 약 30분이 소요됩니다.
```
## AWS Management Console 액세스
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/dc5f8ae4-0456-45d8-89d5-331b49608cc3)

```
지침의 맨 위에서 Start Lab을 클릭하여 실습을 시작합니다.

Start Lab 패널이 열리고 실습 상태가 표시됩니다.

“Lab status: ready” 메시지가 표시되면 X를 클릭하여 Start Lab 패널을 닫습니다.

지침의 맨 위에서 AWS를 클릭합니다.

그러면 새 브라우저 탭에서 AWS Management Console이 열립니다. 시스템에서 자동으로 로그인합니다.

팁: 새 브라우저 탭이 열리지 않는 경우 일반적으로 브라우저에서 팝업 창을 열 수 없음을 나타내는 배너 또는 아이콘이 브라우저 상단에 표시됩니다. 배너 또는 아이콘을 클릭하고 Allow pop ups를 선택합니다.

이러한 지침이 나란히 표시되도록 AWS Management Console 탭을 정렬합니다. 두 브라우저 탭이 동시에 표시되어 실습 단계를 보다 쉽게 수행할 수 있게 됩니다.

 

과제 1: VPC 생성
이 과제에서는 VPC 마법사를 사용하여 단일 가용 영역에 인터넷 게이트웨이 1개와 서브넷 2개가 있는 VPC를 생성합니다. IGW(인터넷 게이트웨이)는 VPC의 인스턴스와 인터넷 간의 통신을 허용하는 VPC 구성 요소입니다.

VPC를 생성했다면 서브넷을 추가할 수 있습니다. 각 서브넷은 하나의 가용 영역 내에 모두 상주하며, 여러 영역에 분산할 수 없습니다. 서브넷의 트래픽이 인터넷 게이트웨이로 라우팅되는 경우 해당 서브넷을 퍼블릭 서브넷이라고 합니다. 서브넷에 인터넷 게이트웨이에 대한 경로가 없는 경우 해당 서브넷을 프라이빗 서브넷이라고 합니다.

또한 이 마법사에서는 프라이빗 서브넷의 EC2 인스턴스에 대한 인터넷 연결을 제공하는 데 사용되는 NAT 게이트웨이를 생성합니다.

AWS Management Console의 Services  메뉴에서 VPC를 클릭합니다.

Launch VPC Wizard을 클릭합니다.

왼쪽 탐색 창에서 두 번째 옵션인 VPC with Public and Private Subnets를 클릭합니다.

선택(Select)을 클릭하고 다음을 구성합니다.

VPC name: Lab VPC
Availability zone: 첫 번째 가용 영역 선택
Public subnet name: Public Subnet 1
Availability Zone: 첫 번째 가용 영역 선택(위에서 사용한 것과 동일한 가용 영역)
Private subnet name: Private Subnet 1
Elastic IP Allocation ID: 확인란을 클릭하고 표시되는 IP 주소 선택
Create VPC을 클릭합니다.

마법사가 VPC를 생성합니다.

완료되면 OK을 클릭합니다.

   동일한 가용 영역에 퍼블릭 서브넷 및 프라이빗 서브넷이 있고 각 서브넷에 대한 라우팅 테이블이 있는 VPC가 프로비저닝되었습니다.

  퍼블릭 서브넷의 CIDR은 10.0.0.0/24입니다. 이는 10.0.0.x로 시작되는 모든 IP 주소가 퍼블릭 서브넷에 포함된다는 것을 의미합니다.

   프라이빗 서브넷의 CIDR은 10.0.1.0/24입니다. 이는 10.0.1.x로 시작되는 모든 IP 주소가 프라이빗 서브넷에 포함된다는 것을 의미합니다.
```
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/1d5d8281-05fc-4fb0-8309-ebdbdb68f641)

