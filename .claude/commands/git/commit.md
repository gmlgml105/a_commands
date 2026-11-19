---
description: .gitignore 설정, origin 연결, prefix 규칙에 맞춘 커밋 후 push
argument-hint: [커밋 메시지]
---

# Git 커밋 & Push

아래 순서대로 작업해 줘. 각 단계의 **생략 조건**에 해당하면 그 단계는 건너뛰고 다음 단계로 넘어가.

## 1. `.gitignore` 작성

- **생략 조건:** 프로젝트 루트에 `.gitignore`가 이미 있으면 이 단계는 생략해.
- 없으면 새로 만들고 아래 항목을 모두 포함해 줘.
  - **에디터:** VSCode (`.vscode/`)
  - **OS:** macOS (`.DS_Store` 등), Windows (`Thumbs.db`, `desktop.ini` 등)
  - **환경변수:** `.env`, `.env.*` 등 일반적인 환경변수 파일
    - 단, `.env.example`은 제외하지 말고 커밋되도록 둬.

## 2. remote 연결

- **생략 조건:** `origin`이 이미 연결되어 있으면 이 단계는 생략해. (`git remote -v`로 확인)
- 연결되어 있지 않으면 아래 주소를 `origin`이라는 이름으로 추가해 줘.

```bash
git remote add origin git@github.com:gmlgml105/a_commands.git
```

## 3. 커밋

- 커밋 메시지: `$ARGUMENTS`
- 메시지 내용과 변경 사항을 보고 아래 규칙 중 알맞은 prefix를 골라 붙여 줘.
- 형식: `<prefix>: <커밋 메시지>` (예: `feat: 로그인 기능 추가`)

### 커밋 prefix 규칙

| prefix | 용도 |
| --- | --- |
| `feat` | 새로운 기능 추가 |
| `fix` | 버그 수정 |
| `docs` | 문서 수정 (README 등) |
| `style` | 코드 포맷 변경 (세미콜론, 공백 등) |
| `refactor` | 리팩토링 (기능 변화 없음) |
| `test` | 테스트 코드 추가/수정 |
| `chore` | 빌드, 설정, 패키지, 기타 작업 |
| `perf` | 성능 개선 |
| `ci` | CI 설정 수정 |
| `build` | 빌드 시스템 수정 |
| `revert` | 커밋 되돌리기 |

## 4. Push

- 커밋이 끝나면 `origin`으로 push 해 줘.
- 처음 push하는 브랜치라면 upstream을 함께 설정해 줘.

```bash
git push -u origin <현재 브랜치>
```
