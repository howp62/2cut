# 인생투컷 📷

> 4장 연속 촬영 후 마음에 드는 2장을 골라 꾸미고 저장하는 웹 포토부스

**🔗 라이브 데모**: [https://howp62.github.io/2cut/](https://howp62.github.io/2cut/)

---

## 주요 기능

| 단계 | 기능 |
|------|------|
| 📷 촬영 | 첫 장만 버튼을 누르면 3초 간격으로 4장 자동 연속 촬영 |
| 🖼️ 선택 | 찍은 4장 중 마음에 드는 2장 선택 |
| 🎨 꾸미기 | SVG 스티커 · 타이포그래피 · 흰 테두리 + 날짜 추가 |
| 💾 저장 | PNG / JPG 다운로드 (300 DPI, 2.1 × 3.4인치) |

---

## 꾸미기 기능

### 🎨 SVG 스티커
- 하트, 별, 왕관, 다이아, 달, 반짝, 꽃, 리본, 구름, 번개, 음표, 나비 등 **13종**
- **10가지 색상** 선택 가능
- 선택한 스티커의 색상 실시간 변경
- 드래그로 자유롭게 위치 조정

### ✏️ 텍스트
- **5가지 Google Fonts**: Black Han Sans · 주아체 · 개구체 · Noto Sans KR · Pacifico
- 8가지 색상 · 크기 슬라이더
- 드래그로 자유롭게 위치 조정

### 🖼️ 흰 테두리 + 날짜
- 인생네컷 스타일 흰 테두리 프레임
- 날짜 자동 입력 (수정 가능)

---

## 기술 스택

- **단일 파일** (`index.html`) — HTML + CSS + JavaScript 인라인
- **외부 의존성**: Google Fonts CDN 전용 (UI 라이브러리 없음)
- **카메라**: `navigator.mediaDevices.getUserMedia`
- **이미지 합성**: HTML5 Canvas API
- **저장**: `<a download>` / iOS는 새 탭에서 길게 누르기

---

## 출력 사양

| 항목 | 값 |
|------|-----|
| 해상도 | 630 × 1020 px |
| 실제 크기 | 2.1 × 3.4 인치 |
| 인쇄 품질 | 300 DPI |
| 포맷 | PNG (무손실) / JPG (품질 0.95) |

---

## 로컬 실행

```bash
# 1. 저장소 클론
git clone https://github.com/howp62/2cut.git
cd 2cut

# 2. 로컬 서버 실행 (HTTPS 없이 카메라 사용 불가)
npx serve .
# 또는
python3 -m http.server 3000

# 3. 브라우저에서 열기
# http://localhost:3000
```

> ⚠️ `getUserMedia`는 **HTTPS** 또는 **localhost** 환경에서만 동작합니다.  
> 스마트폰에서 테스트하려면 ngrok 등 HTTPS 터널이 필요합니다.

---

## 스마트폰 홈화면 앱으로 추가

1. Safari / Chrome에서 [라이브 데모](https://howp62.github.io/2cut/) 접속
2. **공유 버튼** → **홈 화면에 추가**
3. 홈 화면에 **"2컷"** 아이콘으로 설치됨

---

## 브라우저 호환성

| 브라우저 | 카메라 | 저장 |
|---------|--------|------|
| Chrome (Android/PC) | ✅ | ✅ 다운로드 폴더 |
| Safari (iOS) | ✅ HTTPS 필요 | ✅ 길게 누르기 → 사진 앱 |
| Firefox | ✅ | ✅ |
| Samsung Internet | ✅ | ✅ |
