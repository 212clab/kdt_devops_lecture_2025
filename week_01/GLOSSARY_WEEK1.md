# Week 1 용어집 - DevOps 기초 및 이론

## 📖 Week 1 핵심 용어 정리

Week 1에서 다루는 DevOps 문화, 조직 변화, 도구 생태계 관련 핵심 용어들을 정리했습니다.

---

## 🏢 DevOps 문화 및 조직

### **DevOps**
- **정의**: Development(개발) + Operations(운영)의 합성어
- **핵심**: 기술이 아닌 **문화와 철학**
- **목표**: 빠르고 안정적인 소프트웨어 배포

### **CALMS 모델**
- **C**ulture (문화): 협업과 신뢰 기반 문화
- **A**utomation (자동화): 반복 작업 자동화
- **L**ean (린): 낭비 제거와 가치 중심
- **M**easurement (측정): 데이터 기반 의사결정
- **S**haring (공유): 지식과 책임 공유

### **Conway's Law (콘웨이 법칙)**
- **정의**: "조직 구조가 시스템 구조를 결정한다"
- **의미**: 팀 구조와 소프트웨어 아키텍처의 상관관계
- **DevOps 적용**: Cross-functional Team 구성의 중요성

### **Silo Effect (사일로 현상)**
- **정의**: 부서 간 단절과 소통 부족 현상
- **문제**: 책임 전가, 느린 배포, 높은 실패율
- **해결**: DevOps 문화를 통한 협업 강화

---

## 🔄 개발 방법론

### **Waterfall Model (워터폴 모델)**
- **특징**: 순차적 단계별 진행
- **단계**: 요구사항 → 설계 → 구현 → 테스트 → 배포
- **문제점**: 긴 주기, 늦은 피드백, 변경 어려움

### **Agile (애자일)**
- **핵심**: 짧은 반복(Sprint)을 통한 점진적 개발
- **가치**: 개인과 상호작용, 작동하는 소프트웨어
- **DevOps 연관**: 빠른 피드백과 지속적 개선

### **CI/CD (Continuous Integration/Continuous Deployment)**
- **CI**: 지속적 통합 - 코드 변경사항을 자주 통합
- **CD**: 지속적 배포 - 자동화된 배포 파이프라인
- **효과**: 빠른 배포, 높은 품질, 신속한 피드백

---

## 🛠 DevOps 도구 생태계

### **Version Control (버전 관리)**
- **Git**: 분산 버전 관리 시스템
- **GitHub**: Git 기반 협업 플랫폼
- **GitLab**: 통합 DevOps 플랫폼
- **Bitbucket**: Atlassian의 Git 솔루션

### **CI/CD 도구**
- **Jenkins**: 오픈소스 자동화 서버
- **GitHub Actions**: GitHub 통합 CI/CD
- **GitLab CI**: GitLab 내장 CI/CD
- **Azure DevOps**: Microsoft의 DevOps 플랫폼

### **Container Technology (컨테이너 기술)**
- **Docker**: 컨테이너 플랫폼의 표준
- **Kubernetes**: 컨테이너 오케스트레이션
- **Container Registry**: 이미지 저장소 (Docker Hub, ECR)

### **Cloud Platforms (클라우드 플랫폼)**
- **AWS**: Amazon Web Services
- **Azure**: Microsoft Azure
- **GCP**: Google Cloud Platform
- **특징**: 확장성, 유연성, 관리형 서비스

---

## 📊 DevOps 메트릭

### **DORA Metrics**
- **Deployment Frequency**: 배포 빈도
- **Lead Time**: 변경사항 배포까지 소요 시간
- **MTTR**: 평균 복구 시간
- **Change Failure Rate**: 변경 실패율

### **SLA/SLO/SLI**
- **SLA**: Service Level Agreement (서비스 수준 협약)
- **SLO**: Service Level Objective (서비스 수준 목표)
- **SLI**: Service Level Indicator (서비스 수준 지표)

---

## 🏭 실제 사례 기업

### **Netflix**
- **특징**: 클라우드 네이티브, 마이크로서비스
- **성과**: 하루 수천 번 배포
- **기술**: Chaos Engineering, 자동화된 복구

### **Amazon**
- **특징**: Two-Pizza Team, 높은 자율성
- **성과**: 11.7초마다 배포
- **문화**: "You build it, you run it"

### **Google**
- **특징**: SRE(Site Reliability Engineering) 문화
- **기술**: Kubernetes, Istio 등 오픈소스 기여
- **철학**: "Error Budget" 개념 도입

---

## 🔧 DevOps 실천 방법

### **Infrastructure as Code (IaC)**
- **정의**: 인프라를 코드로 관리
- **도구**: Terraform, CloudFormation, Ansible
- **장점**: 버전 관리, 재현 가능성, 자동화

### **Monitoring & Logging (모니터링 & 로깅)**
- **목적**: 시스템 상태 파악과 문제 해결
- **도구**: Prometheus, Grafana, ELK Stack
- **원칙**: 모든 것을 측정하고 알림 설정

### **Security (보안)**
- **DevSecOps**: 개발 과정에 보안 통합
- **Shift Left**: 개발 초기 단계부터 보안 고려
- **자동화**: 보안 스캔과 컴플라이언스 체크

---

## 💡 핵심 원칙

### **DevOps 3 Ways**
1. **Flow**: 개발에서 운영까지의 흐름 최적화
2. **Feedback**: 빠른 피드백 루프 구축
3. **Continual Learning**: 지속적 학습과 실험

### **Lean Principles (린 원칙)**
- **Value**: 고객 가치 중심
- **Value Stream**: 가치 흐름 최적화
- **Flow**: 흐름 개선
- **Pull**: 필요에 따른 당김 방식
- **Perfection**: 완벽을 향한 지속적 개선

---

## 📚 추가 학습 키워드

### **고급 개념**
- **Chaos Engineering**: 장애 상황 시뮬레이션
- **Canary Deployment**: 점진적 배포
- **Blue-Green Deployment**: 무중단 배포
- **Feature Toggle**: 기능 플래그

### **조직 문화**
- **Blameless Postmortem**: 비난 없는 사후 분석
- **Psychological Safety**: 심리적 안전감
- **Learning Organization**: 학습하는 조직
- **Servant Leadership**: 서번트 리더십

---

*이 용어집은 Week 1의 이론적 기초를 다지는 데 도움이 됩니다. Week 2에서는 이러한 개념들을 실제로 구현하는 방법을 학습합니다.*
