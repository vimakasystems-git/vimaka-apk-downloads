# CerebroBrasil — instaladores

Pipeline de build (GitHub Actions) para:
- **Android .apk** (Capacitor 6, wrapper do app publicado em https://cerebrobrasil-com-br.base44.app)
- **Windows .exe** (Tauri 2, NSIS)

## Disparar um release

Faça push de uma tag `cerebrobrasil-vX.Y.Z` ou rode o workflow manualmente em Actions.

O CI publica (pré-release) com SHA-256:
- `CerebroBrasil-Android.apk` (debug-signed na primeira versão)
- `CerebroBrasil-Setup.exe` (NSIS)

## Assinatura de produção (Android)

Adicione os secrets do repo (`ANDROID_KEYSTORE` base64, `ANDROID_KEY_ALIAS`, `ANDROID_KEY_PASSWORD`, `ANDROID_STORE_PASSWORD`) e troque `assembleDebug` por `assembleRelease` no workflow.

## App alvo

https://cerebrobrasil-com-br.base44.app
