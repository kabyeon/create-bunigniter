# 🔥 create-bunigniter

**BunIgniter 프로젝트 스캐폴딩 도구**

CodeIgniter 3 스타일의 Bun 풀스택 MVC 프레임워크 [BunIgniter](https://github.com/kabyeon/bunigniter)를 한 번의 명령어로 시작하세요.

## 🚀 사용법

```bash
bunx create-bunigniter@latest my-app
```

```bash
bunx create-bunigniter@latest blog
```

실행하면 다음을 자동으로 수행합니다:

1. 📁 프로젝트 디렉토리 생성
2. 📦 `bunigniter` 패키지 설치
3. 🏗️ `bunigniter init` 으로 프로젝트 스캐폴딩

## 📋 사전 요구사항

- [Bun](https://bun.sh) >= 1.0.0

## 🎯 생성 후

```bash
cd my-app
bun run dev
```

`http://localhost:3000` 에서 확인할 수 있습니다.

## ⌨️ CLI 명령어

프로젝트 생성 후 사용 가능한 명령어:

```bash
bun run bi make:scaffold post --fields=title:string,content:text  # CRUD 전체 생성
bun run bi make:scaffold post --api --fields=title:string         # API 전용
bun run bi migrate                                               # 마이그레이션
bun run bi migrate:rollback                                      # 롤백
bun run bi db:seed                                               # 시드 실행
bun run bi list:routes                                           # 라우트 목록
```

## 🔗 관련 링크

| 링크 | 설명 |
|------|------|
| [BunIgniter](https://github.com/kabyeon/bunigniter) | 프레임워크 레포지토리 |
| [문서](https://github.com/kabyeon/bunigniter/tree/main/docs/user-guide) | 기능별 상세 가이드 |
| [Bun](https://bun.sh) | Bun 런타임 |

## 📜 라이선스

MIT
