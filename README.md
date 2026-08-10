# Je-Seok Ham — 개인 홈페이지

`index.html` 파일 하나로 되어 있습니다. Jekyll이나 빌드 과정이 없어서, 파일만 고치고 push하면 몇 초 뒤 사이트에 바로 반영됩니다.

## 폴더 구조

```
JeSeokHam.github.io/
├── index.html              ← 내용 수정은 전부 여기서
├── .nojekyll               ← 지우지 마세요 (GitHub Pages 빌드 스킵용)
└── assets/
    ├── profile.jpg         ← 프로필 사진 (정사각형, 400×400 이상 권장)
    ├── CV_JeSeokHam.pdf    ← CV
    └── papers/             ← 논문 main figure 이미지
        ├── cee2026.png
        ├── omnipredict.png
        ├── llamaped.png
        ├── cipf.png
        ├── mcip.png
        └── iscas2021.png
```

이미지 파일이 아직 없어도 사이트는 깨지지 않습니다. 회색 자리표시 박스가 대신 보이고, 파일을 올리는 순간 그림으로 바뀝니다.

## 1. GitHub Pages에 올리기

1. GitHub에 로그인 → 새 저장소 만들기
2. 저장소 이름을 **`JeSeokHam.github.io`** 로 정확히 입력 ← 대소문자 그대로
3. **Public** 선택 → Create repository
4. `Add file` → `Upload files` 로 이 폴더 안의 내용물을 전부 드래그해서 업로드 → Commit
5. `Settings` → `Pages` 로 이동, Source를 **Deploy from a branch**, 브랜치를 **main / (root)** 로 지정 → Save

1~2분 뒤 https://jeseokham.github.io/ 에서 사이트가 열립니다.

## 2. 두 개의 링크

| 용도 | 주소 |
|---|---|
| **수정용** | https://github.com/JeSeokHam/JeSeokHam.github.io/edit/main/index.html |
| **공개용** | https://jeseokham.github.io/ |

수정용 링크로 들어가면 브라우저에서 바로 HTML을 고치고 `Commit changes`를 누를 수 있습니다. 터미널이나 에디터 없이도 됩니다.

## 3. 논문 그림 넣는 법

논문 PDF에서 Figure 1(또는 overview figure)을 캡처해서 PNG로 저장한 뒤 `assets/papers/`에 올리면 됩니다.

- 권장 비율: **가로:세로 = 16:10** (레이아웃이 이 비율로 잘라냅니다)
- 권장 크기: 가로 800~1200px
- 파일 용량은 300KB 이하로 줄이는 걸 추천합니다 (https://tinypng.com)

파일 이름을 위 구조와 다르게 하고 싶으면 `index.html`의 `src="assets/papers/..."` 부분만 바꾸면 됩니다.

## 4. 논문 추가하는 법

`index.html`에서 `<div class="pub">` 로 시작하는 블록을 통째로 복사해서 원하는 연도 그룹 안에 붙여넣고 내용만 바꾸면 됩니다.

```html
<div class="pub">
  <img class="pub-fig" src="assets/papers/새논문.png" alt="..."
       data-label="ICCV 2026&#10;main figure">
  <div>
    <p class="pub-title">논문 제목</p>
    <p class="pub-authors"><span class="me">Je-Seok Ham</span>, 공저자들</p>
    <p class="pub-venue"><em>학회 이름</em>, 2026</p>
    <p class="pub-note">Oral Presentation</p>   <!-- 필요 없으면 이 줄 삭제 -->
    <div class="pub-links">
      <a href="논문링크" target="_blank" rel="noopener">Paper</a>
      <a href="코드링크" target="_blank" rel="noopener">Code</a>
    </div>
  </div>
</div>
```

새 연도를 추가할 때는 `<div class="year-group">` 블록을 복사하고 `year-label`의 숫자를 바꾸세요.

## 5. 색상 / 폰트 바꾸기

`index.html` 상단 `:root { ... }` 안의 값만 고치면 전체 톤이 한 번에 바뀝니다.

```css
--accent: #1d4e89;   /* 링크와 강조색. 여기만 바꿔도 분위기가 확 달라집니다 */
```

## 확인이 필요한 부분

아래 항목은 공개된 정보로 채워둔 것이라 직접 확인하고 고쳐주세요.

- [ ] ETRI 재직 기간 (현재 2019–2023으로 적어둠)
- [ ] Texas A&M 협업 항목 — 실제 형태에 맞게 수정하거나 삭제
- [ ] Awards 섹션 — 내용이 비어 있음 (없으면 섹션째 삭제)
- [ ] Academic Activities의 Reviewer 목록
- [ ] Google Scholar / LinkedIn 링크의 `YOUR_ID` 부분 (GitHub 링크는 채워둠)
- [ ] OmniPredict, ISCAS 논문의 정확한 URL (현재 임시 링크)
