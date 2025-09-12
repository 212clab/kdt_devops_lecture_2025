# Week 4: Kubernetes 기초 (실습 중심)

## 📅 일정 개요
- **학습 방식**: 이론 40% + 실습 60%
- **전제 조건**: Week 3 Docker Compose 완료
- **목표**: Kubernetes 기본 개념과 오브젝트 실습

## 🎯 학습 목표
- Kubernetes 아키텍처 및 핵심 개념 이해
- 클러스터 구성 및 기본 오브젝트 학습
- kubectl 명령어 마스터
- Pod, Service, Deployment 실습

## 🔄 Docker → Kubernetes 전환
```
Docker Compose → Kubernetes:
├── docker-compose.yml → YAML 매니페스트
├── 서비스 정의 → Pod, Service, Deployment
├── 네트워크 → Kubernetes 네트워킹
└── 볼륨 → PersistentVolume, PVC
```

## 📚 주간 일정

### Day 1: Kubernetes 개념 및 아키텍처
**세션 1-2**: Kubernetes란 무엇인가? Docker와의 차이점
**세션 3-4**: 마스터 노드와 워커 노드 아키텍처
**세션 5-6**: etcd, API Server, Scheduler, Controller Manager
**세션 7-8**: kubelet, kube-proxy, Container Runtime

### Day 2: 로컬 Kubernetes 환경 구성
**세션 1-2**: Minikube 설치 및 설정
**세션 3-4**: kubectl 설치 및 기본 명령어
**세션 5-6**: Kind, k3s 등 대안 도구 소개
**세션 7-8**: 실습: 첫 번째 클러스터 생성 및 접근

### Day 3: Pod와 기본 오브젝트
**세션 1-2**: Pod 개념 및 생명주기
**세션 3-4**: YAML 매니페스트 작성법
**세션 5-6**: 라벨과 셀렉터 활용
**세션 7-8**: 실습: Pod 생성, 수정, 삭제

### Day 4: Service와 네트워킹
**세션 1-2**: Service 타입별 특징 (ClusterIP, NodePort, LoadBalancer)
**세션 3-4**: Endpoint와 서비스 디스커버리
**세션 5-6**: DNS 및 네트워크 정책
**세션 7-8**: 실습: 서비스를 통한 Pod 노출

### Day 5: Deployment와 ReplicaSet
**세션 1-2**: Deployment 개념 및 롤링 업데이트
**세션 3-4**: ReplicaSet과 스케일링
**세션 5-6**: 롤백 및 히스토리 관리
**세션 7-8**: 종합 실습: 완전한 애플리케이션 배포

## 🛠 실습 환경
- **로컬 클러스터**: Minikube, Kind, 또는 Docker Desktop Kubernetes
- **클라우드 옵션**: AWS EKS, Google GKE (선택사항)
- **도구**: kubectl, Helm (기초)

## 📊 학습 방식 (이론 40% + 실습 60%)
```
각 세션 구성 (50분):
├── 개념 설명 (20분) - 40%
├── 실습 진행 (25분) - 50%
└── 문제 해결 및 Q&A (5분) - 10%
```

---
**이전**: [Week 3 - Docker 심화 및 Compose](../week_03/README.md)  
**다음**: [Week 5 - Kubernetes 심화 및 운영](../week_05/README.md)
