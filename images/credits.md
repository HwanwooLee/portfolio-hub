# 이미지 출처

| 파일 | 쓰인 곳 | 출처 | 만든 사람 | 라이선스 |
|---|---|---|---|---|
| `hangar-sky.jpg` | 타이틀·출격·로비 배경의 원경 (격납고 문 너머 노을 하늘과 도시 실루엣) | [Unsplash: Vibrant orange sky at dusk over city skyline](https://unsplash.com/photos/vibrant-orange-sky-at-dusk-over-city-skyline-fKTIbKo-kWE) | [xiao ying (@zh369_)](https://unsplash.com/@zh369_) | [Unsplash License](https://unsplash.com/license) — 무료, 상업적 이용 가능, 출처 표시 의무 없음(표시함) |

## 사진을 어떻게 썼는지

- 원본을 가로 2400 × 세로 1100px로 잘라서 썼다 (오른쪽 아래 도시 부분, 가로등이 나온 왼쪽은 잘라냄). 색 보정은 하지 않았다.
- 사진에 사람은 나오지 않는다.
- 실제 사진은 **노을 진 도시**다. 화면에서 불타는 폐허처럼 보이는 것은 그 위에 코드로 그린 것이다:
  무너진 건물·크레인 실루엣, 불길, 연기, 불씨, 격납고 구조물은 전부 Three.js(WebGL)로 실시간 렌더링한다.
- 실제 전쟁·재난 현장 사진은 쓰지 않았다.

## 그 밖에

- 3D 라이브러리: [three.js](https://threejs.org/) r160 (MIT License), jsDelivr CDN에서 불러옴
- 출격 연출의 소리는 Web Audio API로 직접 합성했다. 음원 파일이나 다른 게임의 효과음을 쓰지 않았다.
- 배경음악과 효과음(마우스 올림 "틱", 클릭 "철컥")도 Web Audio API로 직접 합성했다. 다른 게임·영화의 음악이나 효과음을 쓰지 않았다.
