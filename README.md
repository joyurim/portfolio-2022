# portfolio-2022

### meta tag 기본

- meta name="viewport" : 모바일 브라우저의 화면 가로 크기
- content=width=device-width : 컨텐츠의 가로길이를 각 디바이스의 크기에 맞춤
- initial-scale=1.0 : 최초 화면 크기, 1.0은 100%의 비율
- minimum-scale=1.0 : 화면을 줄열을 때 최소 화면 크기
- maximum-scale=1.0 : 화면을 늘렸을 때 최대 화면 크기
- user-scalable=no : 사용자가 화면을 축소할 수 없게 함

### IOS 대응

- <mata content="viewport-fit=cover"> : 컨텐츠가 노치 부분까지 커버 됨
- <mata name="format=detectopm" content="telephone=no"> : 전화번호가 링크화 되는것 방지
- <link rel="apple-touch-icon-precomposed" href=".png"> : 파비콘의 아이폰 버전 (사이즈 72x72 권장)

### 모바일 웹 ui 초기화 코드

```css
// 모바일에서는 %로 작업하기 때문에 border나 padding을 넣을경우 100%가 넘어가서 레이아웃이 깨짐
*,
*:after,
*:before {
  box-sizing: border-box;
}

// 아이폰에서는 body의 크기를 자동으로 잡아주지 않아 히든이 안걸려서 레이아웃이 깨짐.
// position: fixed로 띄운 뒤 가로, 세로 100%로 크기를 직접 지정해주면 아이폰 하위 버전에서 바디에 히든을 걸 수 있다.
body.on {
  overflow: hidden;
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}

// min-width 설정
// pc : 1200px pr 1280px  || mobile : 320px
body > div {
  min-width: 320px;
}

// mobile 탭 하이라이트
a {
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0.1);
}
```
