# 🚀 Project: the-aio Website Rebuilding (Hugo + GitHub)

이 문서는 기존 the-aio.com의 콘텐츠를 유지하면서, GitHub Pages에서 운영 가능한 고성능 Hugo 사이트로 이전하기 위한 가이드라인입니다.

---

## 1. 개발 환경 준비
가장 먼저 본인의 컴퓨터에 아래 도구들을 설치해야 합니다.
* **Hugo Extended 버전:** (SASS/SCSS 지원을 위해 반드시 'Extended' 버전 필요)
* **Git:** 코드 관리 및 GitHub 배포용
* **VS Code:** 웹사이트 수정을 위한 에디터

---

## 2. Hugo 프로젝트 초기화
터미널(또는 CMD)에서 아래 명령어를 순서대로 입력하여 프로젝트 뼈대를 만듭니다.

```bash
# 1. 새로운 Hugo 사이트 생성 (프로젝트명: antigravity)
hugo new site antigravity

# 2. 폴더 이동 및 Git 초기화
cd antigravity
git init
```

---

## 3. 테마 선정 및 적용
`the-aio`는 AI 기술 기업이므로 **비즈니스/포트폴리오형 테마**를 추천합니다. 

* **추천 테마:** * [Blowfish](https://themes.gohugo.io/themes/blowfish/) (세련된 다크모드 지원)
    * [Congo](https://themes.gohugo.io/themes/congo/) (미니멀하고 깔끔함)
    * [Hugo Agency](https://themes.gohugo.io/themes/hugo-agency/) (기업 홍보에 최적화)

* **테마 적용 예시 (Blowfish 기준):**
```bash
git submodule add https://github.com/nunocoracao/blowfish.git themes/blowfish
```
* 그 후 `hugo.toml` 파일에서 `theme = "blowfish"`를 설정합니다.

---

## 4. 콘텐츠 마이그레이션 전략
기존 사이트의 내용을 아래와 같이 마크다운(`.md`) 파일로 재구성합니다.

| 기존 메뉴 | Hugo 경로 | 포맷 | 비고 |
| :--- | :--- | :--- | :--- |
| **회사 소개** | `content/_index.md` | Hero Section | 메인 화면에 회사 비전 배치 |
| **주요 서비스** | `content/services/*.md` | Card UI | AI 솔루션별 개별 파일 생성 |
| **포트폴리오** | `content/projects/*.md` | Grid Layout | 기존 실적 이미지와 설명 이관 |
| **문의하기** | `content/contact.md` | HTML Form | Formspree 등 외부 API 연동 |

---

## 5. GitHub Pages 자동 배포 (GitHub Actions)
GitHub에 코드를 올리면 자동으로 웹사이트가 빌드되도록 설정합니다.

1. 프로젝트 루트에 `.github/workflows/hugo.yml` 파일을 만듭니다.
2. [Hugo 공식 배포 스크립트](https://gohugo.io/hosting-and-deployment/hosting-on-github/)를 복사해서 붙여넣습니다.
3. GitHub 저장소 설정(`Settings > Pages`)에서 소스를 **GitHub Actions**로 변경합니다.

---

## 6. 향후 유지보수 장점
* **보안:** 데이터베이스가 없어 해킹 위험이 거의 없습니다.
* **속도:** 전 세계 어디서든 1초 미만으로 로딩됩니다.
* **비용 0원:** 서버 호스팅 비용이 전혀 들지 않습니다.
* **버전 관리:** 모든 수정 내역이 Git에 기록됩니다.
