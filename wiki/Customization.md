# Customization

## README 수정 방법

### 기본 수정

1. [GitHub에서 직접 편집](https://github.com/minjungsung/minjungsung/edit/main/README.md) 또는 로컬 클론 후 편집
2. `README.md` 파일의 내용을 수정
3. `main` 브랜치에 push하면 프로필에 즉시 반영

### 프로젝트 추가/수정

`README.md`의 "What I'm Building" 테이블에 새 프로젝트를 추가하려면:

```html
<tr>
<td width="50%">

**[🆕 프로젝트명](URL)** — 한 줄 설명
<br/>
상세 설명
<br/><br/>
`기술1` `기술2` `기술3`
<br/>
[Demo](URL) · [Source](URL)

</td>
<td width="50%">
  <!-- 다른 프로젝트 -->
</td>
</tr>
```

### 배지 커스터마이징

[Shields.io](https://shields.io/)를 사용하여 커스텀 배지를 생성할 수 있습니다:

```markdown
[![배지텍스트](https://img.shields.io/badge/-텍스트-색상코드?style=flat-square&logo=로고이름&logoColor=white)](링크)
```

예시:
```markdown
[![Gmail](https://img.shields.io/badge/-email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:email@gmail.com)
```

### 기술 스택 업데이트

"Tech DNA" 섹션의 테이블을 직접 수정합니다. 이모지 + 카테고리 + 기술 목록으로 구성됩니다.

## 3D 기여 그래프 설정

### 개요

3D 기여 그래프는 [`yoshi389111/github-profile-3d-contrib`](https://github.com/yoshi389111/github-profile-3d-contrib) GitHub Action으로 자동 생성됩니다.

### 동작 방식

1. GitHub Actions 워크플로우가 정기적으로 실행
2. GitHub 기여 데이터를 수집
3. 3D SVG 그래프를 생성하여 `profile-3d-contrib/` 디렉토리에 저장
4. 자동 커밋 + push

### 워크플로우 설정

`.github/workflows/profile-3d.yml`:

```yaml
name: GitHub Profile 3D Contrib
on:
  schedule:
    - cron: '0 6 * * *'  # 매일 UTC 06:00
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: minjungsung
      - name: Commit & Push
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "github-actions[bot]@users.noreply.github.com"
          git add -A
          git diff --cached --quiet || git commit -m "chore: update 3D contribution graph"
          git push
```

### 테마 변경

기본 테마 외에 다양한 테마를 사용할 수 있습니다:

| 테마 | 파일명 |
|------|--------|
| Night Rainbow (현재 사용) | `profile-night-rainbow.svg` |
| Green | `profile-green.svg` |
| Gitblock | `profile-gitblock.svg` |
| South Season | `profile-south-season.svg` |
| Night View | `profile-night-view.svg` |

README에서 이미지 경로를 변경하여 테마를 바꿀 수 있습니다:

```markdown
![](./profile-3d-contrib/profile-night-rainbow.svg)
```

### 트러블슈팅

**그래프가 업데이트되지 않는 경우:**
1. Actions 탭에서 워크플로우 실행 상태 확인
2. `GITHUB_TOKEN` 권한 확인 (contents: write 필요)
3. 수동으로 `workflow_dispatch` 실행

**SVG가 깨지는 경우:**
- GitHub의 SVG 렌더링 캐시 문제일 수 있음
- `?v={timestamp}`를 이미지 URL에 추가하여 캐시 무효화

## 프로필 README 팁

### Markdown 팁

- **HTML 테이블 사용** — 복잡한 레이아웃에 유용 (GitHub Markdown에서 `<table>`, `<tr>`, `<td>` 지원)
- **Center 정렬** — `<div align="center">` 사용
- **이미지 크기 조절** — `<img width="400" src="...">` 사용
- **배지** — [Shields.io](https://shields.io/) + [Simple Icons](https://simpleicons.org/) 조합

### 참고 자료

- [Awesome GitHub Profile READMEs](https://github.com/abhisheknaiidu/awesome-github-profile-readme) — 영감 받기
- [GitHub Profile README Generator](https://rahuldkjain.github.io/gh-profile-readme-generator/) — 자동 생성 도구
- [Shields.io](https://shields.io/) — 배지 생성
- [Simple Icons](https://simpleicons.org/) — 기술 아이콘 검색
