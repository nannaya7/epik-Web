# 찾아오는 길 지도 수정

- 현재 홈페이지 적용 파일: `images/location-map.png` — 사용자가 새로 첨부한 빨간색 핀 지도 원본을 수정 없이 적용했다.
- 이전 ImageGen 수정본 보관: `design-assets/location-map-clean.png` (홈페이지에 사용하지 않음)
- 사용자 제공 원본 보관: `design-assets/location-map-original.png`
- 편집 가능한 합성 원본: `design-assets/location-map-clean.svg`
- 방식: 내장 ImageGen으로 주황색 원을 지운 이미지를 생성한 뒤, 원의 선 주변만 마스크로 원본 지도에 합성했다. 원본 도로·지명은 유지하고 청록색 위치 핀을 SVG로 추가했다. 최종 PNG는 SVG를 렌더링한 파일이다.

## ImageGen 최종 프롬프트

Use case: precise-object-edit. Edit target: the supplied Korean street map screenshot used on a company's directions section. Remove ONLY the hand-drawn orange irregular circle surrounding the label 인천테크노밸리 U1센터 near the upper middle of the image (approximately x=750-936, y=327-470 in the 1567x1584 input). Restore the tiny bits of pale gray building/map background covered by the orange stroke. Do not add a pin, text, or new graphic: a precise location marker will be added as a separate website overlay later. Invariants: keep the entire map, original crop, aspect ratio, layout, streets, rivers, parks, transit lines, station labels and EVERY original Korean label identical to the input. This is minimal erasure/inpainting of the orange circle only, not a recreated or stylized map. All pixels away from the orange stroke should be unchanged. Opaque background.
