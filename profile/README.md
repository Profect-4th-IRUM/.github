# Come2us — E-Commerce 플랫폼

## 어떤 프로젝트인가요?

트래픽 증가 상황을 가정한 MSA 기반 전자상거래 플랫폼으로,
세 차례의 아키텍처 고도화를 거쳤습니다.

## 아키텍처 변화
- 1차: 모놀리식 아키텍처
- 2차: MSA 아키텍처 (ECS + Spring Cloud)
- 3차: MSA 아키텍처 (Kubernetes + Istio)

## 레포지토리 구조
### Backend
| 레포지토리 | 설명 | 프로젝트 차수 |
| --- | --- | --- |
| [mvp-server](https://github.com/Profect-4th-IRUM/mvp-server) | Monolithic 개발 레포 | 1차 |
| [member-service](https://github.com/Profect-4th-IRUM/member-service) | 회원/인증 서비스 | 2•3차 |
| [product-service](https://github.com/Profect-4th-IRUM/product-service) | 상품/카테고리 서비스 | 2•3차 |
| [order-service](https://github.com/Profect-4th-IRUM/order-service) | 주문/쿠폰 서비스 | 2•3차 |
| [payment-service](https://github.com/Profect-4th-IRUM/payment-service) | 결제 서비스 | 2•3차 |
| [global-module](https://github.com/Profect-4th-IRUM/global-module) | MSA 서비스 공통 모듈 | 2•3차 |
| [open-feign-client](https://github.com/Profect-4th-IRUM/open-feign-client) | Open Feign Client 공통 모듈 | 2•3차 |
| [config-repo](https://github.com/Profect-4th-IRUM/config-repo) | application.yaml 중앙 관리용 레포 | 2차 |
| [api-gateway](https://github.com/Profect-4th-IRUM/api-gateway) | Spring Cloud API Gateway 레포 | 2차 |
| [service-discovery](https://github.com/Profect-4th-IRUM/service-discovery) | Netflix Eureka 레포 | 2차 |

### DevOps
| 레포지토리 | 설명 | 프로젝트 차수 |
| --- | --- | --- |
| [come2us-infra-terraform](https://github.com/Profect-4th-IRUM/come2us-infra-terraform) | EC2를 통한 단일 서비스 배포 | 1차 |
| [come2us-infra-terraform-sprint2](https://github.com/Profect-4th-IRUM/come2us-infra-terraform-sprint2) | ECS Fargate를 통한 MSA 서비스 배포 | 2차 |
| [jenkins-pipelines](https://github.com/Profect-4th-IRUM/jenkins-pipelines) | Jenkins 파이프라인 | 2차 |
| [come2us-eks](https://github.com/Profect-4th-IRUM/come2us-eks) | EKS를 통한 MSA 서비스 배포 | 3차 |
| [come2us-gitops](https://github.com/Profect-4th-IRUM/come2us-gitops) | ArgoCD GitOps 레포 (Helm, Istio 매니페스트) | 3차 |