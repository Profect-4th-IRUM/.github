# Come2us — E-Commerce 플랫폼

## 어떤 프로젝트인가요?

트래픽 증가 상황을 가정한 MSA 기반 전자상거래 플랫폼으로,
세 차례의 아키텍처 고도화를 거쳤습니다.

## 아키텍처 변화
- 1차: 모놀리식 아키텍처
- 2차: MSA 아키텍처 (ECS + Spring Cloud)
- 3차: MSA 아키텍처 (Kubernetes + Istio)

### 차수별 특징
| 차수 | 주요 특징 | 배포환경 | CI/CD |
| --- | --- | --- | --- |
| 1차 | Monolith MVP | EC2 | GitHub Actions |
| 2차 | MSA 전환, 낙관적 락 적용 | ECS Fargate | Jenkins + Terraform |
| 3차 | Kafka 도입, 서비스 메시 도입 | EKS + Istio | GitHub Actions + ArgoCD |

📑[2차 설계서](https://bal1oon.oopy.io/2bbadc51-d61a-80eb-97d9-db99ba832263) 📑[3차 설계서](https://bal1oon.oopy.io/2bbadc51-d61a-8060-a580-c06514dd5733)

## 레포지토리 구조
### Backend
| 레포지토리 | 설명 | 프로젝트 차수 |
| --- | --- | --- |
| [mvp-server](https://github.com/Profect-4th-IRUM/mvp-server) | Monolithic 개발 레포 | 1차 |
| [member-service](https://github.com/Profect-4th-IRUM/member-service) | 회원/인증 서비스 | 2•3차 |
| [product-service](https://github.com/Profect-4th-IRUM/product-service) | 상품/카테고리 서비스 | 2•3차 |
| [order-service](https://github.com/Profect-4th-IRUM/order-service) | 주문/쿠폰 서비스 | 2•3차 |
| [payment-service](https://github.com/Profect-4th-IRUM/payment-service) | 결제 서비스 | 2•3차 |
| [api-gateway](https://github.com/Profect-4th-IRUM/api-gateway) | Spring Cloud API Gateway 레포 | 2차 |
| [service-discovery](https://github.com/Profect-4th-IRUM/service-discovery) | Netflix Eureka 레포 | 2차 |
| [config-server](https://github.com/Profect-4th-IRUM/config-server) | config 중앙화 서버 | 2차 |

### DevOps
| 레포지토리 | 설명 | 프로젝트 차수 |
| --- | --- | --- |
| [come2us-infra-terraform](https://github.com/Profect-4th-IRUM/come2us-infra-terraform) | EC2를 통한 단일 서비스 배포 | 1차 |
| [come2us-infra-terraform-sprint2](https://github.com/Profect-4th-IRUM/come2us-infra-terraform-sprint2) | ECS Fargate를 통한 MSA 서비스 배포 | 2차 |
| [jenkins-pipelines](https://github.com/Profect-4th-IRUM/jenkins-pipelines) | Jenkins 파이프라인 | 2차 |
| [come2us-eks](https://github.com/Profect-4th-IRUM/come2us-eks) | EKS를 통한 MSA 서비스 배포 | 3차 |
| [come2us-gitops](https://github.com/Profect-4th-IRUM/come2us-gitops) | ArgoCD GitOps 레포 (Helm, Istio 매니페스트) | 3차 |

---
## Links

보다 자세한 내용은 아래 링크들을 통해 확인 부탁드립니다.

🔗 [2차 발표 자료](https://www.canva.com/design/DAHCgPapfU8/Se_nQ38n1tg2ihQ2iFy05g/view?utm_content=DAHCgPapfU8&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=hceff89ae4a) \
🔗 [최종 발표 자료](https://www.canva.com/design/DAHCgMLvBQU/zf3Y3HgDsdM3xJDewaaY5g/view?utm_content=DAHCgMLvBQU&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=hcce0a6f7c8)