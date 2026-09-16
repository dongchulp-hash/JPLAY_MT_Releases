# JPLAY Music Teller Releases

JPLAY Music Teller는 JPLAY가 HQPlayer로 재생하는 현재 곡을 감지하고, 부족한 음악 정보를 보완해 한국어 감상 해설을 만들어 주는 로컬 웹앱입니다. 로컬 MinimServer 음원과 TIDAL 재생을 지원하며, 앨범 아트와 재생 상태를 보면서 이전 곡·재생/일시정지·다음 곡을 제어할 수 있습니다.

감상 가이드, 음악 에세이, 작품 해설, 오디오파일 관점 중 원하는 스타일을 선택할 수 있으며, 가사가 발견되는 곡은 한국어 가사 해설도 만들 수 있습니다. Mac 또는 Windows PC에서 서버가 실행되고, 같은 네트워크의 iPad·iPhone·PC 브라우저에서 화면을 볼 수 있습니다.

이 저장소는 JPLAY Music Teller의 지인·동호인 대상 설치판을 제공하는 공개 배포 저장소입니다.

프로그램 소스와 개발 문서는 비공개 저장소에서 관리합니다. 이 공개 저장소의 **Releases** 메뉴에는 검증된 macOS·Windows 설치 파일과 SHA-256 체크섬만 게시합니다.

## 지원 환경

- macOS Apple Silicon(M1 이후, macOS 12 이상)
- macOS Intel x86_64(macOS 10.15 Catalina 이상)
- Windows 10·11 x64
- HQPlayer 4·5·6 네트워크 제어 환경

HQPlayer에서 네트워크 제어를 허용해야 하며, MusicTeller를 실행하는 Mac/PC와 HQPlayer가 같은 사설 네트워크에 있어야 합니다. iPad나 iPhone에서도 보려면 해당 기기 역시 같은 네트워크에 연결합니다.

## 설치 파일 받기

오른쪽의 **Releases** 또는 [현재 권장 베타 v5.0.0-beta.4](https://github.com/dongchulp-hash/JPLAY_MT_Releases/releases/tag/v5.0.0-beta.4)에서 운영체제에 맞는 파일을 내려받습니다.

- Apple Silicon Mac: `JPLAY_MT-버전-macOS-arm64.pkg`
- Intel Mac: `JPLAY_MT-버전-macOS-x86_64.pkg`
- Windows 10·11: `JPLAY_MT-버전-Windows-x64-Setup.exe`

현재 V5 설치판은 지인 검증을 위한 베타입니다. Intel Mac 사용자는 Catalina에서 Finder 실행 문제가 수정된 `v5.0.0-beta.4` 이상을 사용해야 합니다.

## 처음 실행 전에 준비할 것

### 1. MusicBrainz 연락처

MusicBrainz는 곡·작품·작곡가·연주자 정보를 보완할 때 사용합니다. 일반 조회에는 API 키나 MusicBrainz 계정이 필요하지 않습니다. 대신 서비스 정책에 맞는 요청 식별을 위해 연락 가능한 이메일 주소 또는 개인 웹 주소 하나를 설정 화면에 입력합니다.

- MusicBrainz API 안내: <https://musicbrainz.org/doc/MusicBrainz_API>

### 2. AI API 키 하나 이상

한국어 해설을 만들려면 아래 제공자 중 **하나 이상의 개발자 API 키**가 필요합니다. 세 가지를 모두 준비할 필요는 없으며, 키가 등록된 모델만 선택해 사용할 수 있습니다.

- OpenAI: [API 키 발급](https://platform.openai.com/api-keys) 후 [Billing](https://platform.openai.com/settings/organization/billing/overview)에서 결제 수단이나 크레딧을 확인합니다.
- Anthropic Claude: [Claude Console](https://platform.claude.com/)에서 계정을 만든 뒤 API 키와 사용 크레딧을 설정합니다.
- Google Gemini: [Google AI Studio API Keys](https://aistudio.google.com/apikey)에서 Gemini API 키를 만듭니다. 무료 할당량과 사용 가능한 모델은 계정·지역·현재 정책에 따라 달라질 수 있습니다.

ChatGPT Plus/Pro, Claude Pro/Max, Google AI 요금제 같은 일반 사용자 구독은 개발자 API 이용권과 별개입니다. 실제 해설 생성에는 선택한 제공자의 API 요금 또는 무료 할당량이 적용됩니다.

LRCLIB은 가사 검색에 사용하며 별도의 API 키가 필요하지 않습니다. 다만 모든 곡의 가사가 제공되는 것은 아닙니다.

API 키를 GitHub, 메신저, 스크린샷 또는 이슈에 올리지 마세요. 첫 실행 설정 화면에만 입력하면 macOS Keychain 또는 Windows DPAPI 저장소에 보관됩니다.

## 간단한 설치와 사용법

1. 위의 **설치 파일 받기**에서 운영체제에 맞는 설치 파일을 내려받아 설치합니다.
2. HQPlayer 설정에서 네트워크 제어를 허용하고 JPLAY로 곡을 재생합니다.
3. 응용 프로그램의 `JPLAY Music Teller`를 처음 한 번 실행합니다.
4. 브라우저 설정 화면에 MusicBrainz 연락처와 사용할 AI API 키를 입력하고 `안전하게 저장하고 시작`을 누릅니다.
5. 상단 장치 버튼을 눌러 현재 곡을 재생하는 HQPlayer를 선택합니다. 자동으로 발견되지 않으면 HQPlayer의 IP 주소나 호스트명을 직접 추가합니다.
6. 화면에 현재 곡이 나타나면 필요에 따라 `곡 정보 추가 찾기`를 눌러 MusicBrainz 정보를 보완합니다.
7. MusicTeller 카드에서 AI 모델과 해설 스타일을 선택한 뒤 `한국어 해설 만들기`를 누릅니다.
8. 가사가 있는 곡은 `가사 해설`을 눌러 가사의 의미와 맥락을 한국어로 읽습니다.

서버 Mac/PC에서는 `http://127.0.0.1:8765`로 접속합니다. 같은 네트워크의 iPad·iPhone에서는 `http://서버의-IP주소:8765`를 엽니다. Windows 방화벽 안내가 나타나면 개인 네트워크에서만 접근을 허용합니다.

## 보안 안내

- 설치 파일은 반드시 이 저장소의 GitHub Release에서 받으세요.
- 함께 제공되는 SHA-256 체크섬과 다운로드한 파일을 비교하세요.
- API 키는 설치 파일에 포함되지 않습니다.
- macOS에서는 Keychain, Windows에서는 현재 사용자 DPAPI 암호화 저장소에 API 키를 보관합니다.
- 서명되지 않은 베타에서는 macOS Gatekeeper 또는 Windows SmartScreen 경고가 나타날 수 있습니다.
- 출처를 확인할 수 없는 설치 파일에는 보안 예외를 허용하지 마세요.

## API 사용료와 개인정보

음악 해설에는 OpenAI, Anthropic 또는 Google Gemini 중 하나 이상의 개발자 API 키가 필요합니다. ChatGPT·Claude·Gemini의 일반 구독료와 API 사용료는 별도입니다.

일반 해설을 만들면 화면의 곡 메타데이터가 사용자가 선택한 AI 제공자에게 전송됩니다. 가사 해설은 곡 메타데이터로 LRCLIB을 조회하고, 일치한 가사를 선택한 AI 제공자에게 전송합니다.

## 비공식 프로젝트

이 저장소는 개인이 개발한 비공식 프로젝트입니다. JPLAY, Signalyst/HQPlayer, OpenAI, Anthropic 또는 Google과 제휴하거나 공식 지원을 받지 않습니다. 각 제품명과 상표는 해당 소유자에게 있습니다.

문제를 제보할 때는 사용한 Release 버전, 운영체제 버전과 증상을 전달해 주세요. API 키, 이메일 주소, 스트리밍 URL 토큰이나 개인 음원 경로는 공개 게시물에 올리지 마세요.
