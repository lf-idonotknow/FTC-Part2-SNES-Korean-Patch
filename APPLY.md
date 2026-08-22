# BPS 패치 적용 방법

## 준비물

- `FTC-Part2-SNES-Korean-Patch-v0.9.1.bps`
- BPS 형식을 지원하는 패치 도구
- 적법하게 준비한 일본판 V1.0 NP headerless 원본 ROM

지원 원본 SHA-256:

```text
472c87ee9c10a69c45b447246fb29c815c79b56884a8b37172ccf48991e037fb
```

## 그래픽 도구로 적용

1. [Floating IPS](https://github.com/Alcaro/Flips) 또는 호환 BPS 패치 도구를 실행합니다.
2. `Apply Patch`를 선택합니다.
3. 이 저장소의 `.bps` 파일을 선택합니다.
4. 지원 원본 ROM을 선택합니다.
5. 출력 ROM의 저장 위치와 이름을 지정합니다.

BPS 내부에는 원본·출력 크기와 CRC32가 기록되어 있습니다. 원본이 다르면 체크섬 오류를 무시하지 말고 정확한 원본을 다시 확인하십시오.

## 명령행 Floating IPS

```sh
flips --apply \
  FTC-Part2-SNES-Korean-Patch-v0.9.1.bps \
  'Famicom Tantei Club Part II (J) (V1.0) (NP).smc' \
  'Famicom Tantei Club Part II (Korean) v0.9.1.smc'
```

`--ignore-checksum` 옵션은 사용하지 마십시오.

## 결과 검증

macOS:

```sh
shasum -a 256 'Famicom Tantei Club Part II (Korean) v0.9.1.smc'
```

Linux:

```sh
sha256sum 'Famicom Tantei Club Part II (Korean) v0.9.1.smc'
```

Windows PowerShell:

```powershell
Get-FileHash '.\Famicom Tantei Club Part II (Korean) v0.9.1.smc' -Algorithm SHA256
```

정상 결과:

```text
d7d6c56ff0f70be6482e422e4a788779f03951af00851526f27938088715c3ae
```

## 실행 전 주의

- 이전 한국어 개발판의 세이브 스테이트를 불러오지 마십시오.
- 새 ROM을 깨끗하게 부팅하고 게임 자체 SRAM을 사용하십시오.
- 원본 또는 결과 해시가 다르면 해당 파일로 플레이하거나 오류를 제보하기 전에 적용 절차를 다시 확인하십시오.
