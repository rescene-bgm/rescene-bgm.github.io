# 안원잘부 BGM 아카이브

걸그룹 리센느(RESCENE)의 유튜브 채널 콘텐츠 **"안녕하세요원이입니다잘부탁드립니다"(안원잘부)** 영상에 사용된 BGM을 에피소드별 타임라인으로 정리한 팬 아카이브입니다.

👉 **https://rescene-bgm.github.io/**

A fan-made archive of the background music used in RESCENE's YouTube series *안원잘부*, organized as a scene-by-scene timeline for each episode.

---

## 주요 기능

- **장면과 브금을 함께**: 위에는 원본 영상(NOW SHOWING), 아래에는 그 장면의 BGM(SOUNDTRACK). 이전 / 다음으로 넘기면 두 화면이 함께 바뀝니다.
- **타임라인**: 에피소드별 장면 시간·장면 묘사·곡명·아티스트를 한눈에. 시간을 누르면 원본 영상이 그 장면으로 이동합니다.
- **검색**: 곡명, 아티스트, 장면 묘사로 전체 에피소드를 검색합니다.
- **TOP 차트**: 많이 재생된 곡, 많이 담긴 곡 순위(익명 집계).
- **나만의 플레이리스트**: 곡을 담아 연속 재생하고, 끌어서 순서를 바꾸고, 링크로 공유할 수 있습니다.
- **모바일 대응**: 하단 탭, 장면 카드 스와이프, 가로 모드 전용 배치, 홈 화면에 추가(앱처럼 전체 화면으로 실행).
- **PC 단축키**: `←` `→` 이전 / 다음 장면, `Space` 재생 / 일시정지, `/` 검색, `Esc` 검색 닫기.
- **테마**: 보라 · 파랑 · 초록 · 주황 · 핑크 · 흑백 · 라이트.

## 파일 구성

```
/
├─ index.html              사이트 전체(HTML · CSS · JS 한 파일)
├─ episodes.json           에피소드 목록
├─ data/
│  ├─ s1_ep1.json          에피소드별 장면 · 곡 목록
│  └─ ...
├─ manifest.webmanifest    홈 화면에 추가(PWA) 설정
├─ icon-192.png            앱 아이콘
├─ icon-512.png
├─ icon-maskable-512.png
├─ apple-touch-icon.png    iPhone 홈 화면 아이콘
├─ og.png                  링크 미리보기 이미지
├─ README.md
└─ LICENSE
```

## 데이터 형식

- `episodes.json`: 에피소드마다 `id`(`s시즌_ep번호`), `season`, `title`, `url`(원본 영상). 새 편은 끝에 덧붙이면 되고, 사이트는 가장 최신 편을 기본으로 엽니다.
- `data/{id}.json`: 장면마다 `t`(등장 시간), `desc`(장면 묘사), `title`, `artist`, `url`(BGM 영상), 선택 항목 `start`(BGM 재생 시작 시간), `extra`(추가 정보), `prev`(BGM 주소를 바꿨을 때 예전 주소, 여러 개면 배열). 시간 순서대로 적습니다.

## 로컬에서 미리 보기

`index.html`을 더블클릭해서 열면 데이터 파일을 읽지 못합니다. 폴더에서 간단한 서버를 띄워 확인하세요.

```bash
python -m http.server
# http://localhost:8000 접속
```

YouTube 플레이어와 공유하기 · 링크 복사 기능은 HTTPS(GitHub Pages)에서 온전히 동작합니다.

## 배포

GitHub Pages(저장소 루트, `main` 브랜치)로 배포합니다. 위 파일들을 모두 저장소 루트에 올리면 됩니다.

## 통계

곡별 재생 · 담기 횟수는 개인 정보 없이 익명으로 집계하고, 방문 통계에는 Google Analytics를 사용합니다.

## 의견 · 제보

곡 정보 오류나 누락은 DC 갤러리 [안원잘부 브금 모음 시리즈](https://gall.dcinside.com/mgallery/board/view/?id=kpopcontent&no=9407)의 해당 편 댓글로 알려 주세요.

## 라이선스

이 저장소의 **코드와 정리된 데이터**는 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.ko)에 따라 출처를 밝히는 비영리 목적에 한해 이용할 수 있습니다. 이를 수정하거나 보태서 만든 결과물도 같은 조건(CC BY-NC-SA 4.0)으로 공개해야 합니다. 자세한 내용은 [LICENSE](LICENSE)를 참고하세요.

팬이 만든 비공식 아카이브이며, **영상과 음악의 저작권은 각 권리자에게 있습니다.** 이 사이트는 영상이나 음원을 저장하거나 배포하지 않으며, 모든 재생은 YouTube 공식 플레이어를 통해 이루어집니다.
