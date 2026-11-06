# EasyDoDiet

오프라인 건강 기록 안드로이드 앱. 걸음 · 체중 · 식단 · 운동 · 운동 중 음악을 한 앱에서 기록하고, 데이터는 기기 밖으로 나가지 않음. EasyDo 시리즈.

버그 · 제안은 [Issues](../../issues)에.

## 다운로드

최신 버전 0.2.2 — [Releases](https://github.com/parkrye/AppProject_EasyDoDiet/releases)에서 `EasyDoDiet-<버전>.apk`를 받아 설치. Android 11 이상.

- 처음 설치 시 "출처를 알 수 없는 앱" 설치 허용 필요. Play 프로텍트가 검사 화면을 띄울 수 있음
- 업데이트는 새 APK를 같은 방식으로 덮어 설치. 기록 · 설정 유지
- 앱 안 업데이트 알림 없음. 설정 → 앱 정보 → `새 버전 받기`로 Releases 페이지 확인
- 서명 인증서 SHA-256: `1a277fae84af21854bee6da6f2aae7fed6bbd4c1022ca9103addd0fca3988b4d`
  (`apksigner verify --print-certs EasyDoDiet-<버전>.apk`로 확인. 각 Release 본문에 APK SHA-256도 있음)

## 기능

| 탭 | 내용 |
|---|---|
| 오늘 | 걸음 · 칼로리 한도 대비 섭취 · 체중 · 그날 식단 · 운동 요약(걸음 · 유산소 총량 포함) |
| 운동 | 러닝 · 걷기 GPS 기록(경로 · 페이스 · 랩 · 음성 안내). 기록 중 경로 실시간 표시 · 음성 안내 켜고 끄기, 맨몸 · 아령 · 기구 운동 세트 · 타이머 · 운동 설명, 운동 달력 |
| 음악 | 기기 음악 재생 · 재생목록. 운동 화면에서 바로 조작 |
| 식단 | 음식 · 레시피 · 끼니 세트 메뉴로 섭취 기록, 목록에 저장하지 않는 일회성 추가 |
| 체중 | 체중 기록 · 기간별 추세. 하루 여러 번 기록하면 그날 평균으로 계산, 기록 목록은 날짜별로 묶어 건마다 수정 · 삭제 |
| 기록 | 기간별(마지막에 고른 기간 유지, 처음은 1개월, 오늘 포함) 칼로리 수지 · 섭취 · 걸음 · 운동 그래프와 이동평균 추세선, 기준선(수지 0 · 표준 체중과 BMI 범위 · 평균 걸음 · 평균 운동). 인바디 측정 기록 · 회차별 변화(요약에는 기간 내 변화). 확인용 PDF(그래프 · 게이지) · 분석용 PDF(날짜별 수치 표) 저장, 분석용 텍스트 공유 |

- 걸음: 기기 걸음 센서, Health Connect 걸음 읽기 선택
- 일상 걸음도 운동: 유산소 기록 밖 걸음을 걷기 운동 칼로리로 환산해 소비량 · 운동 그래프에 포함 (보폭 × 체중)
- 인바디: 결과지 값(체중 · 골격근량 · 체지방량 필수, 체지방률 · BMI · 기초대사량 · 체수분 · 내장지방 · 점수 선택) 입력. 드물게 재는 걸 전제로 기간 대신 측정 회차끼리 비교. 새 측정 체중은 체중 기록에도 추가
- 표준 범위 막대: 체중 · BMI · 체지방량 · 체지방률 · 내장지방을 낮음 · 표준 · 높음 구간 막대와 값 표시로 표시 (오늘 · 기록), 보고서는 결과지형 눈금 막대
- 보고서: 확인용은 본인이 보는 건강검진 · 인바디 결과지 형식, 분석용은 AI 등에 넘기는 순수 데이터(프로필 · 계산식 · 결측 표기 규칙 포함)
- Health Connect로 체중 · 운동 기록 내보내기 선택
- 설정 › 데이터: `백업 만들기`(JSON, 파일명 `easydodiet-backup-yyyy-MM-dd.json`) · `백업에서 복원`(확인 후 실행), CSV 내보내기
- 설정 › 앱 정보: `앱 정보`(버전 · 개인정보 · 저작권) · `새 버전 받기`(Releases 페이지) · `오픈소스 라이선스`

## 개인정보

인터넷 권한 없음 · 광고 없음 · 수집 · 전송 없음.

- 계정 · 사용 통계 · 오류 보고 없음
- 모든 기록은 기기 안 DB에만 저장. 앱 삭제 시 함께 삭제 (Android 자동 백업도 끔)
- 위치는 러닝 · 걷기 기록 중에만 사용. 지도는 타일 없이 경로선만 그림
- Health Connect 연동은 사용자가 켤 때만. Health Connect도 기기 안 저장소
- 백업 · 보고서 파일은 사용자가 고른 위치에만 저장

## EasyDo 시리즈

| 앱 | 용도 | 플랫폼 |
|---|---|---|
| [EasyDoDraw](https://github.com/parkrye/MultiProject_EasyDoDraw) | 그림 · 애니메이션 | Android · Windows |
| [EasyDoWrite](https://github.com/parkrye/AppProject_EasyDoWrite) | 소설 · 글쓰기 | Android |
| [EasyDoRead](https://github.com/parkrye/AppProject_EasyDoRead) | 책 · 문서 읽기 | Android |
| [EasyDoShelve](https://github.com/parkrye/AppProject_EasyDoShelve) | 웹 소설 서재 | Android |
| [EasyDoPhoto](https://github.com/parkrye/AppProject_EasyDoPhoto) | 카메라 · 사진 편집 | Android |
| [EasyDoDiet](https://github.com/parkrye/AppProject_EasyDoDiet) | 식단 · 운동 기록 | Android |
| [EasyDoZip](https://github.com/parkrye/AppProject_EasyDoZip) | 파일 · 압축 관리 | Android |
| [EasyDoGame](https://github.com/parkrye/AppProject_EasyDoGame) | 미니 게임 모음 | Android |
| [EasyDoMix](https://github.com/parkrye/AppProject_EasyDoMix) | 영상 · 오디오 편집 | Android |
| [EasyDoRecord](https://github.com/parkrye/AppProject_EasyDoRecord) | 녹음 | Android |
| [EasyDoStudio](https://github.com/parkrye/DesktopProject_EasyDoStudio) | 화면 녹화 · 영상 편집 | Windows |

## 라이선스

MIT License · © parkrye. 포함된 서드파티 라이브러리 라이선스는 앱 안 `설정 → 앱 정보 → 오픈소스 라이선스`에서 확인.
