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

## 실습 1 : IAM 소개
[AWS labs](https://labs.vocareum.com/main/main.php)
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/43d7fba8-151b-47df-b005-7d08ddf5f164)
```
IAM 소개는 모듈에서 바로 안들어가질 수도 있으므로 위의 링크에서 진행한다. 
```
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/19aa9806-5f84-46b2-b70d-fbdfacbbaea7)
```
AWS Identity and Access Management(IAM)는 Amazon Web Services(AWS) 고객이 AWS에서 사용자와 사용자 권한을 관리할 때 사용할 수 있는 서비스입니다. IAM을 사용하면 사용자, 보안 자격 증명(예: 액세스 키) 및 사용자가 액세스할 수 있는 AWS 리소스를 제어하는 권한을 중앙에서 관리할 수 있습니다.
```

## AWS Management Console 엑세스
```
지침의 맨 위에서 Start Lab을 클릭하여 실습을 시작합니다.

Start Lab 패널이 열리고 실습 상태가 표시됩니다. Start Lab 대화 상자가 열리면 이 실습 뒷부분에서 참조해야 하므로 AWS 리전을 적어둡니다.

“Lab status: ready” 메시지가 표시되면 X를 클릭하여 Start Lab 패널을 닫습니다.

지침의 맨 위에서 AWS를 클릭합니다.

그러면 새 브라우저 탭에서 AWS Management Console이 열립니다. 시스템에서 자동으로 로그인합니다.

팁: 새 브라우저 탭이 열리지 않는 경우 일반적으로 브라우저에서 팝업 창을 열 수 없음을 나타내는 배너 또는 아이콘이 브라우저 상단에 표시됩니다. 배너 또는 아이콘을 클릭하고 Allow pop ups를 선택합니다.

이러한 지침이 나란히 표시되도록 AWS Management Console 탭을 정렬합니다. 두 브라우저 탭이 동시에 표시되어 실습 단계를 보다 쉽게 수행할 수 있게 됩니다.
```

## 사용자 및 그룹 살펴보기
```
AWS Management Console의 Services 메뉴에서 IAM을 클릭합니다.

왼쪽 탐색 창에서 Users를 클릭합니다.

다음 IAM 사용자가 미리 생성되어 있습니다.

user-1
user-2
user-3
user-1을 클릭합니다.

user-1에 대한 요약 페이지가 표시됩니다. Permissions 탭이 표시됩니다.

user-1에는 권한이 없습니다.

Groups 탭을 클릭합니다.

user-1은 그룹의 구성원이 아닙니다.

Security credentials 탭을 선택합니다.

   user-1에 콘솔 암호가 할당됩니다.

왼쪽 탐색 창에서 Groups를 클릭합니다.
   다음 그룹이 이미 생성되어 있습니다.

EC2-Admin
EC2-Support
S3-Support
EC2-Support 그룹을 클릭합니다.
   EC2-Support 그룹에 대한 요약 페이지로 이동합니다.

Permissions 탭을 클릭합니다.
   이 그룹에는 AmazonEC2ReadOnlyAccess라는 관리형 정책이 연결되어 있습니다. 관리형 정책은 IAM 사용자 및 그룹에 연결할 수 있는 사전 구성된 정책입니다(AWS 또는 관리자가 작성). 정책이 업데이트되면 정책에 대한 변경 사항이 정책에 연결된 모든 사용자 및 그룹에 즉시 적용됩니다.

Actions에서 Show Policy 링크를 클릭합니다.
   정책은 특정 AWS 리소스에 대해 허용되거나 거부되는 작업을 정의합니다. 이 정책은 EC2, Elastic Load Balancing, CloudWatch 및 Auto Scaling에 대한 정보를 나열하고 설명할 수 있는 권한을 부여합니다. 리소스를 볼 수 있지만 수정할 수 없는 이 기능은 지원 역할에 할당하기에 적합합니다.

   IAM 정책에서 문의 기본 구조는 다음과 같습니다.

Effect는 권한을 허용할지 거부할지를 말합니다.
Action은 AWS 서비스에 수행할 수 있는 API 호출을 지정합니다(예: cloudwatch:ListMetrics).
Resource는 정책 규칙이 적용되는 엔터티의 범위를 정의합니다(예: 특정 Amazon S3 버킷 또는 Amazon EC2 인스턴스 또는 모든 리소스를 나타내는 *).
Show Policy 창을 닫습니다.
왼쪽 탐색 창에서 Groups를 클릭합니다.
S3-Support 그룹을 클릭합니다.
   S3-Support 그룹에는 AmazonS3ReadOnlyAccess 정책이 연결되어 있습니다.

Actions 메뉴 아래에서 Show Policy 링크를 클릭합니다.
   이 정책에는 Amazon S3의 리소스를 가져오고 나열할 수 있는 권한이 있습니다.

Show Policy 창을 닫습니다.
왼쪽 탐색 창에서 Groups를 클릭합니다.
EC2-Admin 그룹을 클릭합니다.
   이 그룹은 다른 두 그룹과 약간 다릅니다. 여기에는 Managed Policy 대신 하나의 사용자 또는 그룹에만 할당되는 정책인 Inline Policy가 있습니다. 인라인 정책은 일반적으로 일회성 상황에 대한 권한을 적용하는 데 사용됩니다.

Actions에서 Show Policy를 클릭하여 정책을 봅니다.
   이 정책은 Amazon EC2에 대한 정보를 볼 수 있는 권한(Describe)과 인스턴스를 시작하고 중지할 수 있는 기능도 부여합니다.

화면 하단에서 Cancel을 클릭하여 정책을 닫습니다.
```
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/3edfe61f-3047-4542-8951-f6782719de96)
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/c1e3ecff-9600-4d96-bd0f-64fd54c8ae5c)
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/f3bbfbad-c137-4dc8-b150-9274cc23d91c)
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/63e67b04-9249-4e89-964b-7b771c71071c)

## 실습 1 IAM 살펴보기 종료
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/728f93bf-485a-4eb0-b631-71e9ff39f403)
```
소요시간 1시간 30분
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

## 모듈 5 VPC 생성 실습 종료
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/af1faa11-e2c2-4705-a693-4613d1830ab2)
```
1시간 30
```

## AWS Academy Cloud Foundation 모듈 1 ~ 10 사전지식 평점
![image](https://github.com/chihyeonWON/Amazon_Web_Service/assets/58906858/29540122-2ed4-4a1f-ae32-8d667b9d299a)
```
모듈1~10까지의 평점 100.0으로 갱신
```
