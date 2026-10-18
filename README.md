# Guestbook

**SKT FLY AI 9기 DevOps 실습**에서 사용한 Node.js / Express 방명록입니다. EJS 화면과 GitHub Actions 기반 Azure App Service 배포 구성을 포함합니다.

## 기능

- 방명록 목록 조회
- 제목·본문을 입력해 글 작성
- 제목 또는 본문이 없으면 HTTP 400 응답
- 메모리 배열에 글 저장 — **서버를 재시작하면 작성한 글이 사라집니다.**

## 로컬 실행

Node.js와 npm이 있는 환경에서 저장소 루트에서 실행합니다.

```bash
npm ci
npm start
```

브라우저에서 [http://localhost:3000](http://localhost:3000)을 엽니다. 포트는 `PORT` 환경변수로 바꿀 수 있습니다.

## 구성

| 경로 | 내용 |
|---|---|
| [app.js](app.js) | Express 설정, 메모리 저장소, 글 작성 처리 |
| [routes/](routes/) | 목록·기본 라우트 |
| [views/](views/) | EJS 화면 |
| [bin/www](bin/www) | HTTP 서버 시작, 기본 포트 3000 |
| [Dockerfile](Dockerfile) | 교육 당시 컨테이너 빌드 구성 |
| [.github/workflows/](.github/workflows/) | Azure 코드·컨테이너 배포 워크플로 |

배포 워크플로는 실습 당시 Azure 리소스를 대상으로 합니다. 다른 환경에서 재사용하려면 대상 리소스와 GitHub Actions 설정을 자신의 환경에 맞춰야 합니다.

## 라이선스

[MIT](LICENSE)
