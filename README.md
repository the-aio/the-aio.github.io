# the-aio.github.io

원래의 홈페이지는 https://www.the-aio.com 입니다.
이 저장소는 기술 문서와 제품 정보를 위한 Hugo 기반 정적 웹사이트입니다.

## 개요

- 목적: 제품/회사 정보 및 지원 페이지를 정적 사이트로 운영
- 스택: Hugo + Blowfish Theme
- 배포: GitHub 저장소의 main 브랜치 기준으로 운영

## 로컬 실행

1. Hugo 설치
2. 저장소 루트에서 아래 명령 실행

```bash
hugo server -D --bind 0.0.0.0 --port 1313
```

3. 브라우저에서 아래 주소 접속

```text
http://localhost:1313
```

## 빌드

정적 파일 생성:

```bash
hugo
```

생성 결과는 public 폴더에 출력됩니다.

## 주요 경로

- content: 페이지/문서 본문
- assets: 커스텀 CSS 및 빌드 대상 리소스
- static: 이미지, 정적 파일, SD Reader 웹앱 파일
- layouts: partial/shortcode 등 사용자 정의 템플릿
- themes/blowfish: 테마 소스

## 운영 메모

- Product 페이지의 스펙은 각 제품 문서 내 Specification 표를 기준으로 관리
- Support > SD Reader 버튼 및 안내 문구는 content/support.md에서 관리
- SD Reader 웹앱 파일은 static/sd-reader/index.html에서 관리

## 배포 전 체크리스트

1. `hugo` 빌드가 에러 없이 완료되는지 확인
2. 변경된 페이지를 `hugo server -D`에서 직접 확인
3. Product 페이지 이미지/Specification 표가 정상 노출되는지 확인
4. Support > SD Reader 버튼(라이트/다크, hover)이 정상 동작하는지 확인
5. 불필요 파일(`.vscode` 등)이 커밋 대상에 포함되지 않았는지 확인
