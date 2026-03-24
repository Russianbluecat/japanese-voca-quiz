# japanese-voca-quiz
# 🇯🇵 Japanese Vocabulary Quiz

구글 시트의 단어 데이터를 기반으로 동작하는 일본어 단어 퀴즈 앱입니다.  
별도의 서버 없이 GitHub Pages로 배포되며, 단어 추가/수정은 구글 시트에서만 하면 됩니다.

---

## ✨ 주요 기능

- **빈칸 채우기 4지선다** — F열의 예문에서 괄호 안 단어를 맞추는 방식
- **10초 타이머** — 시간 초과 시 자동 오답 처리 후 다음 문제로 이동
- **히라가나 보기** — 정답 확인 후 해당 예문의 히라가나 버전 토글
- **번역 보기** — 파파고에서 예문 번역 결과 바로 열기
- **랜덤 출제** — 전체 단어 중 매번 랜덤으로 10문제 선택
- **인트로 화면** — 전체 단어 수와 퀴즈 규칙 안내

---

## 📊 구글 시트 데이터 구조

시트 이름: `Raw_Data`

| 열 | 컬럼명 | 설명 | 예시 |
|----|--------|------|------|
| A | `Original` | 일본어 단어 | 返事 |
| B | `Hiragana` | 히라가나 표기 | へんじ |
| C | `Meaning` | 한국어 뜻 | 대답, 답장 |
| D | `Sample_Sentence` | 예문 (한자 포함) | 彼からまだ返事が来ていない。 |
| E | `Sample_Sentence_hiragana` | 예문 히라가나 버전 | かれからまだへんじがきていない。 |
| F | `Blank_Sentence` | 빈칸 문제 예문 | 彼からまだ(返事)が来ていない。 |
| G | `Translation` | 예문 한국어 번역 | 그에게서 아직 대답이 오지 않았다. |

> ⚠️ **F열 형식 주의**: 빈칸에 들어갈 단어는 반드시 `(단어)` 형태로 괄호 안에 넣어야 합니다.

---

## 🚀 나만의 퀴즈로 만들기

이 코드를 그대로 가져다 다른 단어장에 적용하려면:

**1. 구글 시트 준비**
- 위 표의 컬럼 구조에 맞춰 시트를 만든다
- 시트 공개 설정: `공유 → 링크가 있는 모든 사용자 → 뷰어`

**2. `index.html` 수정**
```javascript
const SHEET_ID = '여기에_구글_시트_ID_입력';
const SHEET_NAME = '시트_탭_이름';
```
> 구글 시트 URL에서 `/d/` 뒤의 긴 문자열이 `SHEET_ID`입니다.

**3. GitHub Pages 배포**
- GitHub 레포 생성 → `index.html` 업로드
- Settings → Pages → Branch: main → Save
- `https://[username].github.io/[repo-name]/` 로 접속

---

## 🛠 기술 스택

- **Frontend**: Vanilla HTML / CSS / JavaScript (단일 파일)
- **데이터**: Google Sheets gviz API (별도 백엔드 없음)
- **호스팅**: GitHub Pages (무료, 비활성화 없음)
- **폰트**: Noto Serif JP, Noto Sans KR (Google Fonts)

---

## 📁 파일 구조

```
/
└── index.html   # 퀴즈 앱 전체 (HTML + CSS + JS 단일 파일)
```
