# minjungsung — Profile README Wiki

## 리포 설명

이 리포지토리(`minjungsung/minjungsung`)는 GitHub 프로필 페이지에 표시되는 **Profile README**를 관리합니다. GitHub에서 사용자 이름과 동일한 이름의 리포지토리를 생성하면, 해당 리포의 `README.md`가 프로필 페이지 상단에 자동으로 표시됩니다.

**프로필 URL:** [github.com/minjungsung](https://github.com/minjungsung)

## 프로필 README 구조

현재 프로필 README는 다음 섹션으로 구성되어 있습니다:

### 1. 헤더

```markdown
# Minjung Sung
**AI Engineer · Full Stack Developer · MLOps**
```

기술 태그 배지: `LLM` `RAG` `Computer Vision` `React` `Python` `TypeScript` `AWS` `Serverless`

연락처 배지:
- Gmail (`minjungsung1994@gmail.com`)
- LinkedIn (`minjung-sung-2bb6b0117`)
- Portfolio (`portfolio-frontend-silk.vercel.app`)

### 2. 소개 (One-liner)

> I build AI-powered products end-to-end — from training pipelines to production APIs to the frontends people actually use. Currently shipping serverless AI services that run at $0/month.

### 3. 🚀 What I'm Building

2×2 테이블 레이아웃으로 현재 진행 중인 프로젝트를 소개합니다:

| 프로젝트 | 설명 |
|----------|------|
| **HackDigest** | AI 뉴스 다이제스트 — Groq LLM + Cloudflare Workers + GitHub Actions |
| **VisionRAG** | 멀티모달 RAG — 비전 모델 기반 문서 이해 |
| **House Scanner** | 부동산 분석 — React + Vercel |
| **LingoCast** | AI 팟캐스트 언어학습 — Spring Boot + React + Cloudflare Worker |

각 프로젝트에는 기술 스택 태그와 관련 링크(데모, 소스, 구독)가 포함됩니다.

### 4. 📊 3D 기여 그래프

GitHub Actions를 통해 자동 생성되는 3D 기여 그래프가 표시됩니다:

```markdown
![](./profile-3d-contrib/profile-night-rainbow.svg)
```

이 그래프는 `yoshi389111/github-profile-3d-contrib` 액션으로 생성됩니다.

### 5. 💡 Tech DNA

기술 스택을 카테고리별로 정리한 테이블:

| 카테고리 | 기술 |
|----------|------|
| AI / ML | Python, PyTorch, TensorFlow, LangChain, RAG |
| Backend | Spring Boot (Kotlin), FastAPI, Node.js |
| Frontend | React, Next.js, TypeScript, Tailwind CSS |
| Cloud & DevOps | AWS (Lambda, ECS, S3), Vercel, Render, Docker |
| Data | PostgreSQL, Redis, Pinecone, BigQuery |

## Wiki 목차

| 페이지 | 내용 |
|--------|------|
| [Customization](Customization) | README 수정 방법, 3D 기여 그래프 설정 |

## 파일 구조

```
minjungsung/
├── README.md                          # 프로필 README (메인)
├── profile-3d-contrib/                # 3D 기여 그래프 (자동 생성)
│   └── profile-night-rainbow.svg
└── .github/workflows/
    └── profile-3d.yml                 # 3D 그래프 생성 워크플로우
```
