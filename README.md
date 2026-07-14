# playw-social-assets

PLAYW 소셜 배포용 미디어 저장소. **공개 저장소인 이유는 하나** — Buffer API에 미디어 업로드
엔드포인트가 없어서(`VideoAssetInput`은 `url`만 받는다) mp4를 공개 URL로 서빙해야 하기 때문.

## 서빙 방식 — jsDelivr CDN
`every-git/tistory-assets`와 동일한 패턴.

```
https://cdn.jsdelivr.net/gh/every-git/playw-social-assets@main/reels/<슬러그>/video.mp4
https://cdn.jsdelivr.net/gh/every-git/playw-social-assets@main/reels/<슬러그>/cover.jpg
```

⚠️ **jsDelivr는 파일당 20MB 제한.** 릴스 mp4가 이걸 넘으면 CRF를 올려 재인코딩하거나 R2로 옮긴다.
⚠️ 새 파일은 CDN 캐시에 반영되기까지 잠깐 걸릴 수 있다(수십 초).

## 구조
```
reels/<YYYY-MM-DD-슬러그>/
  video.mp4    # 1080x1920 · 릴스 본편
  cover.jpg    # 릴스 커버(썸네일)
```

원본·제작 정본은 `youtube/playw/shorts/episodes/<슬러그>/` (여기엔 배포용 사본만 둔다).
