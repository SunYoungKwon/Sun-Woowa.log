# 이미지 최적화

## webp

1. 설치하기

```
brew install webp
```

2. 이미지 리사이징 및 포맷 변경

```
cwebp [options] input_file -o output_file.webp
```

- `-o outputFileName` : output_file의 이름 지정
- `-lossless` : 무손실로 압축
- `near_lossless int` : 무손실에 가까운 수준으로 압축. 0 ~ 100 사이의 값을 가지며, 기본값은 60
- `-q float` : RGB 채널 압축 정도. 0 ~ 100 사이의 값을 가지며, 기본값은 75
- `-resize width height` : 지정한 width, height 값으로 이미지 크기를 변경
- `-h` : 도움말

## ffmpeg

동영상 포맷 변환을 지원하는 오픈소스

1. 설치하기

```
brew install ffmpeg
```

2. 동영상 포맷 변경

```
ffmpeg -i input_file.gif output.file.mp4
```

## 참고

- [cwebp - WebP](https://developers.google.com/speed/webp/docs/cwebp)
- [FFmpeg](https://www.ffmpeg.org/)

---

[[TOP]](#이미지-최적화) | [[HOME]](https://github.com/SunYoungKwon/Sun-Woowa.log#-what-i-studied-in-woowacourse)
