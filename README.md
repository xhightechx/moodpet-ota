# moodpet-ota

MoodPet (ESP32-S3 Touch AMOLED 2.16) OTA 펌웨어 피드.

- `manifest.json` — `{"version": "x.y.z", "url": "<moodpet.bin raw URL>"}`
- `moodpet.bin` — 해당 버전 펌웨어 이미지

기기는 `manifest.json`의 raw URL을 Wi-Fi 연결 시 확인하고,
버전이 다르면 `url`에서 이미지를 받아 반대 OTA 슬롯에 설치한 뒤 재부팅한다.
부팅 검증에 실패하면 부트로더가 이전 슬롯으로 롤백한다.

## 새 버전 배포

1. moodpet 프로젝트에서 `version.txt` 버전 올리고 `idf.py build`
2. `build/moodpet.bin`을 이 저장소에 복사
3. `manifest.json`의 `version`을 같은 값으로 수정
4. commit + push (main 브랜치)
