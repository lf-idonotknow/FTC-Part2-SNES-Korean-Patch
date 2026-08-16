# 패치 생성·검증 정보

- 버전: `v0.9.0-beta.1`
- 생성일: `2026-08-16`
- 형식: BPS delta
- Floating IPS commit: `ff216a75df0987047a67d7923567dc4482ce07ac`

## 원본

- 크기: `3,145,728`바이트
- SHA-256: `472c87ee9c10a69c45b447246fb29c815c79b56884a8b37172ccf48991e037fb`
- CRC32: `28F450AC`

## 결과

- 크기: `4,194,304`바이트
- SHA-256: `d7d6c56ff0f70be6482e422e4a788779f03951af00851526f27938088715c3ae`
- CRC32: `45AF1F4B`

## 패치

- 파일: `FTC-Part2-SNES-Korean-Patch-v0.9.0-beta.1.bps`
- 크기: `179,619`바이트
- SHA-256: `3c46e34042305bd076b78c25496947f8077ac1f65e6c870e58e84014ae8ba06c`

## 검증

1. 지원 원본과 현재 canonical ROM으로 BPS를 생성했습니다.
2. 생성한 BPS를 지원 원본에 다시 적용했습니다.
3. 역적용 결과와 canonical ROM을 바이트 비교했습니다.
4. 결과는 `cmp=0`이며 두 파일의 SHA-256이 일치했습니다.

검증 명령:

```sh
flips --create --bps-delta source.smc target.smc FTC-Part2-SNES-Korean-Patch-v0.9.0-beta.1.bps
flips --apply FTC-Part2-SNES-Korean-Patch-v0.9.0-beta.1.bps source.smc applied.smc
cmp target.smc applied.smc
shasum -a 256 source.smc target.smc FTC-Part2-SNES-Korean-Patch-v0.9.0-beta.1.bps applied.smc
```
