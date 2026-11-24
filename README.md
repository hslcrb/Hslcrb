<div align="center">

# 이호세 · Rheehose

**설치 없이, 브라우저 안에서 끝까지 동작하는 도구를 만듭니다.**

[포트폴리오](https://www.rheehose.com/) · [rhee.life](https://rhee.life) · [기록](https://www.rheehose.com/blog) · [저장소 전체](https://github.com/hslcrb?tab=repositories) · [연락](https://www.rheehose.com/contact)

</div>

## 소개

이호세입니다. Figma로 화면과 사용 흐름을 설계하고 TypeScript, Python, Java, Rust로 구현합니다. 이미지 편집, 폰트 변환, 자바 컴파일과 실행처럼 원래는 설치가 필요했던 일을 브라우저 안에서 끝내는 쪽을 좋아합니다. 파일이 기기를 떠나지 않으면 개인정보 문제도 같이 줄어들기 때문입니다.

무엇을 만들든 README에 먼저 적는 것이 있습니다. 무엇이 실제로 동작하는지, 어디까지 확인했는지, 무엇이 아직 안 되는지입니다. 화면만 흉내 낸 목업을 완성이라고 부르지 않습니다.

요즘은 브라우저 안에서 도는 IDE, 웹 아카이버, 도시 캐릭터 3D 뷰어를 이어서 다듬고 있습니다.

## 대표 프로젝트

### 1. PlayTheClipse · 브라우저에서 도는 Eclipse 워크벤치

JDK, Eclipse, Oracle, Tomcat을 설치하지 않아도 Java와 JSP 실습이 그대로 돌아가게 만들었습니다. Eclipse Compiler for Java 3.26.0이 Wasm JVM 안에서 `.java`를 컴파일하고, CheerpJ 4.3이 `main`을 실행합니다. `jdbc:oracle:thin:@localhost:1521:xe` 주소로 실제 JDBC 드라이버가 붙고, `.jsp`는 서블릿으로 바뀌어 HTML을 돌려줍니다. 서버는 없습니다.

`Java` `WebAssembly` `JSP` `SQL`
[실행](https://hslcrb.github.io/playtheclipse/) · [소스](https://github.com/hslcrb/playtheclipse) · [개발기](https://github.com/hslcrb/playtheclipse/blob/main/docs/DEVLOG.md) · EPL-2.0

### 2. Wayglass · 웹 아카이버와 로컬 리플레이

Heritrix 3.19.0으로 페이지를 긁고, Rust 코어가 WARC와 WACZ로 묶습니다. 만든 `.wacz` 파일은 다른 기기, 다른 도구에서도 그대로 재생됩니다. 아카이브 자체가 원본이 되도록 옆에 데이터베이스를 두지 않았습니다. CLI는 모든 명령이 `--json` 한 덩어리를 표준출력으로 내고 종료 코드가 문서에 고정되어 있어, 사람과 에이전트가 같은 방식으로 부를 수 있습니다.

`Rust` `Heritrix` `WACZ` `Tauri`
[릴리스 v0.1.0](https://github.com/hslcrb/wayglass/releases/tag/v0.1.0) · [소스](https://github.com/hslcrb/wayglass) · [개발기](https://github.com/hslcrb/wayglass/blob/main/docs/DEVLOG.md) · MIT

### 3. 도시 캐릭터 · 지자체 마스코트를 3D로 다시 세우기

수원이와 고양고양이를 Blender 4.2에서 프리미티브로 다시 만들고, GLB로 묶어 Three.js 뷰어에 올렸습니다. 받침대 위에서 숨쉬고, 기쁨·인사·수줍·놀람 모션으로 바뀌고, 전신 자세 10종을 넘겨 볼 수 있습니다. 공식 이미지를 텍스처로 쓰지 않고 공개된 정면과 측면, 매뉴얼의 비례를 보고 형태를 읽어 만들었습니다. 공식 배포처가 아닌 비공식 팬 프로젝트입니다.

`Blender 4.2` `GLB` `Three.js` `Cloudflare Pages`
[라이브 뷰어](https://krcitychars.rhee.life) · [소스](https://github.com/hslcrb/korea-cities-characters) · [제작기](https://github.com/hslcrb/korea-cities-characters/blob/main/docs/DEVLOG.md) · MIT

### 4. 폰트 스위쳐 · 파일을 올리지 않는 폰트 변환

TTF, OTF, WOFF, WOFF2를 브라우저 안에서 서로 바꿉니다. 파일을 중계 서버로 보내지 않고, 확장자만 바꿔 되는 것처럼 보이게 하지도 않습니다. 원본 윤곽을 그대로 꺼내는 것을 기준으로 삼았고, TTF와 CFF 윤곽의 곡선은 다시 그리지 않습니다.

`TypeScript` `Font` `Cloudflare Pages`
[웹 앱](https://switcher.rhee.life/) · [소스](https://github.com/hslcrb/theswitcher) · [설계와 제약](https://github.com/hslcrb/theswitcher/blob/main/docs/ARCHITECTURE.ko.md) · MIT

### 5. JSONote · JSON 노트와 GitHub 동기화

노트를 JSON 파일로 보관하고, 로컬 폴더에 두거나 GitHub 저장소로 동기화합니다. 외부 에이전트가 노트를 읽고 쓰는 MCP 경로도 함께 열어 두었습니다.

`Next.js` `TypeScript` `MCP` `GitHub API`
[웹 앱](https://jsonote.rheehose.com/) · [소스](https://github.com/hslcrb/jsonote) · Apache-2.0

### 6. HANBOM DATA · 교육 공공데이터를 REST와 MCP로

학교 공지 RSS 82곳, NEIS 데이터셋 4종, 대학 교육 정보 12개 기능을 한 사이트, REST, 그리고 읽기 전용 MCP 도구 78개로 묶었습니다. 에이전트가 데이터를 조회하는 경로에는 쓰기 권한을 두지 않았습니다. 학생이 만든 비공식 서비스이며 학교나 교육청이 운영하는 것이 아닙니다.

`TypeScript` `REST` `MCP` `공공데이터`
[사이트](https://data.hanbom.rhee.life/) · [MCP 설정](https://data.hanbom.rhee.life/mcp-setup) · [소스](https://github.com/hslcrb/mcp-for-hanbom) · Apache-2.0

## 만드는 범위

| 영역 | 하는 일 | 확인할 수 있는 곳 |
| --- | --- | --- |
| 화면 설계와 퍼블리싱 | Figma로 흐름과 상태를 설계하고 HTML·CSS·JavaScript·TypeScript로 구현합니다. 상태가 갈리는 화면은 상태 수만큼 그려 두고 구현합니다. | 폰트 스위쳐, JSONote, LabelStudio |
| 브라우저 시스템 | 컴파일러, JVM, JDBC, 서블릿, WARC, 폰트 윤곽처럼 원래 브라우저 밖에서 돌던 것을 안으로 옮깁니다. | PlayTheClipse, Wayglass |
| 3D | Blender 4.2로 모델링하고 GLB로 최적화해 Three.js와 Cloudflare Pages로 배포합니다. | 도시 캐릭터 |
| AI 에이전트 | MCP 서버, 읽기 전용 도구 세트, 에이전트가 파싱하기 좋은 CLI를 직접 만듭니다. | HANBOM DATA, Wayglass, JSONote |
| 보안 도구 | 암복호화 CLI, 시험장 전파 모니터링 앱, 침투 테스트 프레임워크 한국어화처럼 도구 수준의 작업을 합니다. | pycryptor-cli, KoriyoSCAN |

## 그 밖의 작업

- **[imchips](https://github.com/hslcrb/imchips)** · 여러 이미지를 한 번에 리사이즈하거나 다른 형식으로 저장하는 브라우저 이미지 작업실. 이미지 처리는 기기에서 끝납니다. [웹 앱](https://imchips.rhee.life/) · Apache-2.0
- **[dayreco](https://github.com/hslcrb/dayreco)** · 행사 세션이나 회의를 브라우저에서 녹음하고 같은 기기에 저장합니다. 오디오를 서버로 보내지 않습니다. [웹 앱](https://dayreco.rhee.life/) · 소스 공개
- **[Loadit](https://github.com/hslcrb/loadit)** · 다운로드, 선택 텍스트 저장, 여러 페이지를 한 HTML로 아카이빙하는 Chrome 확장. 소스 공개
- **[pyflask_sleek-ytdownloader](https://github.com/hslcrb/pyflask_sleek-ytdownloader)** · Flask와 yt-dlp로 만든 유리질 스타일 미디어 아카이버. Apache-2.0
- **[thedecoder](https://github.com/hslcrb/thedecoder)** · 어셈블리 디스어셈블러 IDE. 제어 흐름을 그림으로 보여줍니다. Apache-2.0
- **[fontchanger](https://github.com/hslcrb/fontchanger)** · 안드로이드 시스템 글꼴을 교체하는 앱. Magisk, KernelSU, Samsung One UI FlipFont를 지원합니다. Apache-2.0
- **[pycryptor-cli](https://github.com/hslcrb/pycryptor-cli)** · AES-256 암복호화 CLI. Termux에서도 돌아갑니다. MIT
- **[KoriyoSCAN](https://github.com/hslcrb/exam-rf-guard_hslcrb)** · 시험 감독관용 안드로이드 앱. 빈 교실의 와이파이와 블루투스 전파를 기록해 두고, 시험 중 새로 잡히는 전파를 표시합니다. 전파를 차단하거나 부정행위를 판정하지는 않습니다.
- **[LabelStudio](https://github.com/hslcrb/LabelStudio)** · FIG 호환 디자인 편집기. `.fig` 압축 파일과 Figma Cloud 문서를 불러오고, 로컬 미디어 보정과 코드 핸드오프까지 한 작업공간에 묶었습니다. TypeScript. 소스 공개
- **[reisian](https://github.com/hslcrb/reisian)** · 코드 없이 화면을 조정해 사이트로 내보내는 로컬 우선 비주얼 스튜디오. Electron, React, TypeScript. MIT
- **[must-have-love-ascii](https://github.com/hslcrb/must-have-love-ascii)** · 한국어 가사를 조선굴림체로 래스터화해 3D 아스키 아트 뮤직비디오로 만든 작품. MIT

## 만드는 방식

1. **기기에서 끝낼 수 있으면 서버를 두지 않습니다.** 이미지, 폰트, 녹음, 컴파일이 그렇습니다. 서버가 없으면 개인정보가 새어 나갈 곳도 없습니다.
2. **한계를 먼저 씁니다.** 안 되는 것, 검증하지 않은 것, 지원하지 않는 형식을 README 첫머리에 적습니다. 지키지 못할 약속을 기능 목록에 넣지 않습니다.
3. **도구는 사람과 에이전트가 같은 방식으로 부를 수 있게 만듭니다.** `--json` 출력, 고정된 종료 코드, 읽기 전용 MCP 도구처럼 양쪽이 같은 계약을 씁니다.
4. **라이선스를 붙입니다.** 공개한 코드에는 MIT, Apache-2.0, EPL-2.0 중 하나를 골라 명시합니다.

## In English

I'm Rheehose (Lee Hose). I design interfaces in Figma and build tools that run entirely in the browser: an Eclipse workbench with a Wasm Java compiler, an Oracle compatible student database and JSP; a WARC/WACZ web archiver whose core is written in Rust; a font converter that never uploads your files; and a Three.js viewer for Korean city mascots I remodeled in Blender.

Every project README states what works, what was verified, and what does not work yet, before it claims to be finished.

<sub>© 2026 Rhee Creative</sub>
