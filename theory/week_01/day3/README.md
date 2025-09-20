# Week 1 Day 3: Docker 이미지 & 네트워킹 & 스토리지

<div align="center">

**📦 이미지 구조 마스터** • **🌐 네트워킹 & 💾 스토리지**

*Dockerfile부터 데이터 영속성까지, Docker 핵심 기능 통합 학습*

</div>

---

## 🕘 일일 스케줄

### 📊 시간 배분
```
📚 이론 강의: 2.5시간 (31.25%) - 50분×3세션
🛠️ 실습 챌린지: 3시간 (37.5%) - 통합 실습
👥 학생 케어: 2.5시간 (31.25%) - 개별 지원 강화
```

### 🗓️ 상세 스케줄
| 시간 | 구분 | 내용 | 목적 |
|------|------|------|------|
| **09:00-09:50** | 📚 이론 1 | Docker 이미지 구조 (50분) | 레이어 시스템 이해 |
| **09:50-10:00** | ☕ 휴식 | 10분 휴식 | |
| **10:00-10:50** | 📚 이론 2 | Dockerfile 작성법 (50분) | 이미지 빌드 마스터 |
| **10:50-11:00** | ☕ 휴식 | 10분 휴식 | |
| **11:00-11:50** | 📚 이론 3 | 네트워킹 & 스토리지 (50분) | 데이터 관리 |
| **11:50-13:00** | 🍽️ 점심 | 점심시간 (70분) | |
| **13:00-16:00** | 🛠️ 챌린지 | 이미지 빌드 & 네트워크 실습 (3시간) | 실무 적용 |
| **16:00-16:15** | ☕ 휴식 | 15분 휴식 | |
| **16:15-18:00** | 👥 케어 | 개별 멘토링 & 회고 (105분) | 맞춤 지원 |

---

## 📚 이론 강의 (2.5시간 - 50분×3세션)

### Session 1: Docker 이미지 구조와 레이어 시스템 (50분)

#### 🎯 학습 목표
- **이해 목표**: Docker 이미지의 레이어 구조와 동작 원리 완전 이해
- **적용 목표**: 이미지 최적화를 위한 레이어 관리 기법 습득
- **협업 목표**: 팀원들과 이미지 구조 분석 및 최적화 방안 토론

#### 🤔 왜 필요한가? (5분)
**현실 문제 상황**:
- 💼 **이미지 크기 문제**: 수 GB 크기의 무거운 이미지로 인한 배포 지연
- 🏠 **일상 비유**: 이사할 때 짐을 효율적으로 포장하는 것과 같은 최적화
- 📊 **시장 동향**: 마이크로서비스 시대에 필수적인 경량 이미지 구축

#### 📖 핵심 개념 (35분)

**🔍 개념 1: 이미지 레이어 구조 (12분)**
> **정의**: Docker 이미지는 여러 개의 읽기 전용 레이어가 쌓인 구조

**레이어 시스템의 장점**:
```mermaid
graph TB
    subgraph "이미지 레이어 구조"
        A[Base Layer<br/>Ubuntu 20.04] --> B[Layer 2<br/>Python 설치]
        B --> C[Layer 3<br/>pip 패키지 설치]
        C --> D[Layer 4<br/>애플리케이션 코드]
        D --> E[Container Layer<br/>실행 시 생성]
    end
    
    F[다른 이미지] --> A
    G[또 다른 이미지] --> B
    
    style A fill:#e3f2fd
    style B,C,D fill:#fff3e0
    style E fill:#e8f5e8
    style F,G fill:#f3e5f5
```

**레이어 공유의 효율성**:
- **저장 공간 절약**: 동일한 베이스 이미지 공유
- **네트워크 효율성**: 변경된 레이어만 다운로드
- **빌드 속도 향상**: 캐시된 레이어 재사용

**🔍 개념 2: 이미지 식별과 태깅 (12분)**
> **정의**: 이미지를 구분하고 관리하기 위한 식별 체계

**이미지 식별 방법**:
```mermaid
graph LR
    A[Image ID<br/>sha256:abc123...] --> B[Repository<br/>nginx]
    B --> C[Tag<br/>latest, 1.21, alpine]
    C --> D[Full Name<br/>nginx:1.21-alpine]
    
    style A fill:#ffebee
    style B fill:#e8f5e8
    style C fill:#fff3e0
    style D fill:#e3f2fd
```

**태깅 전략**:
- **버전 태그**: `app:1.0.0`, `app:1.0.1`
- **환경 태그**: `app:dev`, `app:staging`, `app:prod`
- **특징 태그**: `app:alpine`, `app:slim`

**🔍 개념 3: 이미지 최적화 기법 (11분)**
> **정의**: 이미지 크기를 줄이고 성능을 향상시키는 방법들

**최적화 전략**:
```mermaid
graph TB
    subgraph "이미지 최적화 기법"
        A[멀티스테이지 빌드] --> E[최적화된 이미지]
        B[Alpine Linux 사용] --> E
        C[불필요한 파일 제거] --> E
        D[레이어 수 최소화] --> E
    end
    
    style A,B,C,D fill:#e8f5e8
    style E fill:#4caf50
```

**크기 비교 예시**:
| 베이스 이미지 | 크기 | 용도 |
|---------------|------|------|
| `ubuntu:20.04` | 72MB | 일반적인 용도 |
| `node:18` | 993MB | Node.js 개발 |
| `node:18-alpine` | 174MB | 경량 Node.js |
| `node:18-slim` | 244MB | 중간 크기 |

#### 💭 함께 생각해보기 (10분)

**🤝 페어 토론** (5분):
**토론 주제**:
1. **레이어 이해**: "이미지 레이어가 공유되는 것의 장점은?"
2. **최적화 방안**: "이미지 크기를 줄이는 다양한 방법들은?"
3. **태깅 전략**: "실무에서 효과적인 이미지 태깅 방법은?"

**🎯 전체 공유** (5분):
- **최적화 아이디어**: 이미지 크기 줄이기 방안 공유
- **실무 경험**: 이미지 관리 경험 공유

### Session 2: Dockerfile 작성법과 베스트 프랙티스 (50분)

#### 🎯 학습 목표
- **이해 목표**: Dockerfile 문법과 각 명령어의 역할 완전 이해
- **적용 목표**: 효율적이고 안전한 Dockerfile 작성 능력 습득
- **협업 목표**: 팀원들과 Dockerfile 리뷰 및 개선 방안 토론

#### 📖 핵심 개념 (35분)

**🔍 개념 1: Dockerfile 기본 문법 (12분)**
> **정의**: Docker 이미지를 빌드하기 위한 명령어들을 담은 텍스트 파일

**주요 명령어들**:
```dockerfile
# 베이스 이미지 지정
FROM node:18-alpine

# 메타데이터 추가
LABEL maintainer="developer@company.com"
LABEL version="1.0.0"

# 작업 디렉토리 설정
WORKDIR /app

# 파일 복사
COPY package*.json ./
COPY . .

# 명령어 실행
RUN npm install --production

# 환경 변수 설정
ENV NODE_ENV=production

# 포트 노출
EXPOSE 3000

# 실행 명령어
CMD ["npm", "start"]
```

**명령어별 역할**:
- **FROM**: 베이스 이미지 선택
- **WORKDIR**: 작업 디렉토리 설정
- **COPY/ADD**: 파일 복사
- **RUN**: 빌드 시 명령어 실행
- **CMD/ENTRYPOINT**: 컨테이너 실행 시 명령어

**🔍 개념 2: 멀티스테이지 빌드 (12분)**
> **정의**: 여러 단계로 나누어 최종 이미지 크기를 최소화하는 빌드 방법

**멀티스테이지 빌드 예시**:
```dockerfile
# 빌드 스테이지
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# 프로덕션 스테이지
FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

**멀티스테이지의 장점**:
```mermaid
graph LR
    subgraph "단일 스테이지"
        A1[소스 코드] --> A2[빌드 도구 포함]
        A2 --> A3[큰 이미지<br/>500MB+]
    end
    
    subgraph "멀티 스테이지"
        B1[빌드 스테이지] --> B2[프로덕션 스테이지]
        B2 --> B3[작은 이미지<br/>50MB]
    end
    
    style A3 fill:#ffebee
    style B3 fill:#e8f5e8
```

**🔍 개념 3: Dockerfile 베스트 프랙티스 (11분)**
> **정의**: 효율적이고 안전한 Dockerfile 작성을 위한 권장사항들

**베스트 프랙티스 목록**:
```dockerfile
# ❌ 나쁜 예
FROM ubuntu
RUN apt-get update && apt-get install -y python3 python3-pip curl git
COPY . /app
WORKDIR /app
RUN pip3 install -r requirements.txt
USER root

# ✅ 좋은 예
FROM python:3.9-alpine
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
RUN adduser -D appuser
USER appuser
EXPOSE 8000
CMD ["python", "app.py"]
```

**주요 원칙들**:
- **경량 베이스 이미지**: Alpine Linux 사용
- **레이어 최적화**: RUN 명령어 결합
- **캐시 활용**: 자주 변경되지 않는 파일 먼저 복사
- **보안 강화**: 비root 사용자 사용
- **불필요한 파일 제외**: .dockerignore 활용

#### 💭 함께 생각해보기 (15분)

**🤝 페어 토론** (10분):
**토론 주제**:
1. **문법 이해**: "각 Dockerfile 명령어의 차이점과 사용 시기는?"
2. **최적화 방법**: "멀티스테이지 빌드가 필요한 상황은?"
3. **보안 고려**: "Dockerfile에서 보안을 위해 주의할 점들은?"

**🎯 전체 공유** (5분):
- **베스트 프랙티스**: 효과적인 Dockerfile 작성 팁 공유
- **실습 준비**: 오후 실습에서 작성할 Dockerfile 계획

### Session 3: Docker 네트워킹과 볼륨 관리 (50분)

#### 🎯 학습 목표
- **이해 목표**: Docker 네트워킹 모델과 데이터 영속성 관리 방법 이해
- **적용 목표**: 컨테이너 간 통신과 데이터 보존 실습 능력 습득
- **협업 목표**: 팀원들과 네트워크 구성 및 데이터 관리 전략 토론

#### 📖 핵심 개념 (35분)

**🔍 개념 1: Docker 네트워킹 모델 (12분)**
> **정의**: 컨테이너 간 통신과 외부 네트워크 연결을 위한 시스템

**네트워크 드라이버 종류**:
```mermaid
graph TB
    subgraph "Docker 네트워킹"
        A[bridge<br/>기본 네트워크] --> E[컨테이너 통신]
        B[host<br/>호스트 네트워크] --> E
        C[none<br/>네트워크 없음] --> E
        D[overlay<br/>멀티 호스트] --> E
    end
    
    style A fill:#e8f5e8
    style B fill:#fff3e0
    style C fill:#ffebee
    style D fill:#e3f2fd
```

**네트워크 타입별 특징**:
- **bridge**: 기본 네트워크, 컨테이너 간 통신 가능
- **host**: 호스트 네트워크 직접 사용, 성능 우수
- **none**: 네트워크 연결 없음, 완전 격리
- **overlay**: 여러 Docker 호스트 간 통신

**🔍 개념 2: 볼륨과 데이터 관리 (12분)**
> **정의**: 컨테이너가 삭제되어도 데이터를 보존하는 방법들

**데이터 저장 방식 비교**:
```mermaid
graph TB
    subgraph "데이터 저장 방식"
        A[Volumes<br/>Docker 관리] --> D[데이터 영속성]
        B[Bind Mounts<br/>호스트 경로] --> D
        C[tmpfs<br/>메모리 저장] --> E[임시 데이터]
    end
    
    style A fill:#4caf50
    style B fill:#ff9800
    style C fill:#2196f3
    style D fill:#e8f5e8
    style E fill:#ffebee
```

**각 방식의 특징**:
- **Volumes**: Docker가 관리, 백업과 마이그레이션 용이
- **Bind Mounts**: 호스트 파일시스템 직접 연결
- **tmpfs**: 메모리에 저장, 컨테이너 종료 시 삭제

**🔍 개념 3: 컨테이너 간 통신 (11분)**
> **정의**: 여러 컨테이너가 서로 데이터를 주고받는 방법

**통신 방법들**:
```mermaid
graph LR
    subgraph "컨테이너 통신"
        A[Web Container] --> B[API Container]
        B --> C[Database Container]
        
        A -.-> D[Custom Network]
        B -.-> D
        C -.-> D
    end
    
    style A,B,C fill:#e8f5e8
    style D fill:#fff3e0
```

**통신 설정 예시**:
```bash
# 커스텀 네트워크 생성
docker network create myapp-network

# 데이터베이스 컨테이너 실행
docker run -d --name db --network myapp-network postgres

# 웹 애플리케이션 컨테이너 실행
docker run -d --name web --network myapp-network -p 8080:80 nginx
```

#### 💭 함께 생각해보기 (15분)

**🤝 페어 토론** (10분):
**토론 주제**:
1. **네트워크 선택**: "어떤 상황에서 어떤 네트워크 타입을 사용할까요?"
2. **데이터 관리**: "데이터베이스 컨테이너의 데이터를 어떻게 보존할까요?"
3. **보안 고려**: "컨테이너 간 통신에서 보안을 위한 고려사항은?"

**🎯 전체 공유** (5분):
- **네트워크 전략**: 효과적인 컨테이너 네트워킹 방안
- **데이터 전략**: 안전한 데이터 관리 방법

---

## 🛠️ 실습 챌린지 (3시간)

### 🎯 챌린지 개요
**통합 실습 목표**:
- 커스텀 이미지 빌드부터 네트워크 구성까지 완전 습득
- 실무와 유사한 웹 애플리케이션 환경 구축
- 팀 협업을 통한 복합적 문제 해결

### 📋 챌린지 준비 (15분)
**환경 설정**:
- Dockerfile 작성 환경 준비
- 팀 구성 (3-4명씩)
- 실습 목표 및 평가 기준 공유

### 🚀 Phase 1: 커스텀 이미지 빌드 & 최적화 (90분)

#### 🔧 구현 단계
**Step 1: 기본 웹 애플리케이션 Dockerfile**
```dockerfile
# 기본 Node.js 애플리케이션
FROM node:18-alpine

WORKDIR /app

# package.json 먼저 복사 (캐시 최적화)
COPY package*.json ./
RUN npm install --production

# 애플리케이션 코드 복사
COPY . .

# 비root 사용자 생성
RUN addgroup -g 1001 -S nodejs
RUN adduser -S nextjs -u 1001
USER nextjs

EXPOSE 3000
CMD ["npm", "start"]
```

**Step 2: 멀티스테이지 빌드로 최적화**
```dockerfile
# 빌드 스테이지
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# 프로덕션 스테이지
FROM node:18-alpine AS production
WORKDIR /app
COPY package*.json ./
RUN npm install --production
COPY --from=builder /app/dist ./dist
RUN adduser -D appuser
USER appuser
EXPOSE 3000
CMD ["npm", "start"]
```

**Step 3: 이미지 크기 비교**
```bash
# 이미지 빌드
docker build -t myapp:basic -f Dockerfile.basic .
docker build -t myapp:optimized -f Dockerfile.multi .

# 크기 비교
docker images | grep myapp
```

#### ✅ Phase 1 체크포인트
- [ ] 기본 Dockerfile로 이미지 빌드 성공
- [ ] 멀티스테이지 빌드로 최적화된 이미지 생성
- [ ] 이미지 크기 차이 확인 및 분석
- [ ] 보안을 위한 비root 사용자 설정

### 🌟 Phase 2: 네트워크 구성 & 데이터 영속성 (90분)

#### 🔧 네트워크 및 볼륨 설정
**Step 1: 커스텀 네트워크 생성**
```bash
# 애플리케이션용 네트워크 생성
docker network create webapp-network

# 네트워크 정보 확인
docker network inspect webapp-network
```

**Step 2: 데이터베이스 컨테이너 (볼륨 포함)**
```bash
# PostgreSQL 볼륨 생성
docker volume create postgres-data

# 데이터베이스 컨테이너 실행
docker run -d \
  --name postgres-db \
  --network webapp-network \
  -e POSTGRES_DB=myapp \
  -e POSTGRES_USER=user \
  -e POSTGRES_PASSWORD=password \
  -v postgres-data:/var/lib/postgresql/data \
  postgres:13-alpine
```

**Step 3: 웹 애플리케이션 연결**
```bash
# 웹 애플리케이션 실행
docker run -d \
  --name webapp \
  --network webapp-network \
  -p 8080:3000 \
  -e DATABASE_URL=postgresql://user:password@postgres-db:5432/myapp \
  myapp:optimized
```

**Step 4: 연결 테스트**
```bash
# 컨테이너 간 통신 테스트
docker exec webapp ping postgres-db

# 애플리케이션 로그 확인
docker logs webapp
```

#### ✅ Phase 2 체크포인트
- [ ] 커스텀 네트워크 생성 및 구성
- [ ] 데이터베이스 볼륨 설정 및 데이터 영속성 확인
- [ ] 컨테이너 간 네트워크 통신 성공
- [ ] 웹 애플리케이션 정상 동작 확인

### 🏆 Phase 3: 팀별 통합 프로젝트 (15분)

#### 🤝 팀별 미션
**미션**: 3-tier 웹 애플리케이션 구축

**아키텍처 요구사항**:
```mermaid
graph TB
    A[Load Balancer<br/>Nginx] --> B[Web App 1<br/>Node.js]
    A --> C[Web App 2<br/>Node.js]
    B --> D[Database<br/>PostgreSQL]
    C --> D
    
    E[Redis Cache] --> B
    E --> C
    
    style A fill:#e3f2fd
    style B,C fill:#e8f5e8
    style D fill:#fff3e0
    style E fill:#f3e5f5
```

**팀별 역할 분담**:
- **Frontend 담당**: Nginx 로드 밸런서 설정
- **Backend 담당**: Node.js 애플리케이션 복제 및 설정
- **Database 담당**: PostgreSQL + Redis 구성
- **DevOps 담당**: 네트워크 및 볼륨 통합 관리

### 🎤 결과 발표 및 공유 (30분)
**팀별 발표** (7분×4팀):
- 구축한 아키텍처 설명
- 사용한 Dockerfile과 최적화 방법
- 네트워크 구성 및 데이터 관리 전략
- 팀 협업에서 배운 점과 어려웠던 점

---

## 👥 학생 케어 (105분)

### 🟢 초급자 케어 (집중 지원) - 45분
**개별 멘토링**:
- Dockerfile 문법 완전 이해 확인
- 이미지 빌드 과정에서 발생한 오류 해결
- 네트워킹과 볼륨 개념 재설명
- 실습 결과물 완성도 점검

### 🟡 중급자 케어 (리더십 개발) - 45분
**그룹 멘토링**:
- 이미지 최적화 고급 기법 토론
- 실무에서의 네트워크 보안 고려사항
- 팀 프로젝트 리더십 경험 공유
- 내일 Docker Compose 학습 준비

### 🔴 고급자 케어 (전문성 강화) - 15분
**심화 토론**:
- 컨테이너 보안 스캔 도구 활용
- 이미지 레지스트리 구축 방안
- 네트워크 정책 및 마이크로세그멘테이션
- 오픈소스 기여를 위한 Dockerfile 작성

---

## 📝 일일 마무리

### ✅ 오늘의 성과
- [ ] Docker 이미지 구조와 레이어 시스템 완전 이해
- [ ] Dockerfile 작성 및 멀티스테이지 빌드 습득
- [ ] 컨테이너 네트워킹과 데이터 영속성 구현
- [ ] 팀 협업을 통한 3-tier 아키텍처 구축

### 🎯 내일 준비사항
- **예습**: Docker Compose YAML 문법 기초
- **복습**: 오늘 작성한 Dockerfile 최적화 방안 정리
- **환경**: 멀티 컨테이너 실습을 위한 환경 준비

### 📊 학습 진도 체크
```mermaid
graph LR
    A[Week 1] --> B[Day 1 ✅]
    B --> C[Day 2 ✅]
    C --> D[Day 3 ✅]
    D --> E[Day 4]
    
    style A fill:#4caf50
    style B,C,D fill:#4caf50
    style E fill:#e0e0e0
```

---

<div align="center">

**📦 이미지 빌드 마스터** • **🌐 네트워킹 구성 완료** • **💾 데이터 영속성 구현**

*Docker의 핵심 기능들을 통합적으로 활용할 수 있게 되었습니다*

</div>