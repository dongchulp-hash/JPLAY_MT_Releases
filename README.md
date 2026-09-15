# JPLAY Music Teller Releases

JPLAY Music Teller의 지인·동호인 대상 설치판을 제공하는 공개 배포 저장소입니다.

프로그램 소스와 개발 문서는 [JPLAY_MT](https://github.com/dongchulp-hash/JPLAY_MT) 저장소에서 관리합니다. 이 저장소의 **Releases** 메뉴에는 검증된 macOS·Windows 설치 파일과 SHA-256 체크섬만 게시합니다.

## 지원 환경

- macOS Apple Silicon(M1 이후)
- macOS Intel x86_64
- Windows 10·11 x64
- HQPlayer 4·5·6 네트워크 제어 환경

## 설치 파일 받기

오른쪽의 **Releases** 또는 [최신 Release](https://github.com/dongchulp-hash/JPLAY_MT_Releases/releases/latest)에서 운영체제에 맞는 파일을 내려받습니다.

- Apple Silicon Mac: `JPLAY_MT-버전-macOS-arm64.pkg`
- Intel Mac: `JPLAY_MT-버전-macOS-x86_64.pkg`
- Windows 10·11: `JPLAY_MT-버전-Windows-x64-Setup.exe`

현재 V5 설치판은 지인 검증을 위한 베타입니다. Release가 게시되기 전에는 이 저장소에서 받을 수 있는 공식 설치 파일이 없습니다.

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

문제 제보와 개발 관련 내용은 [JPLAY_MT Issues](https://github.com/dongchulp-hash/JPLAY_MT/issues)를 이용해 주세요. API 키, 이메일 주소, 스트리밍 URL 토큰이나 개인 음원 경로는 이슈에 올리지 마세요.
