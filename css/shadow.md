# Shadow

1. 빛 방향 통일.
2. 수평에 비해 수직이 2배가 되도록 설정하기. 항상 같은 비율로.
3. 그림 그릴 때의 기본 이론과 동일.

## 겹겹이 쌓는 게 더 자연스럽다

```css
  .traditional.box {
    box-shadow:
      0 6px 6px hsl(0deg 0% 0% / 0.3);
  }
```

위의 예제보다 아래의 예제가 훨씬 결과값이 자연스럽다. 단, 오래된 디바이스에서는 렌더링이 느려지는 문제가 생길 수 있으므로 테스트 필수.

```css
  .layered.box {
    box-shadow:
      0 1px 1px hsl(0deg 0% 0% / 0.075),
      0 2px 2px hsl(0deg 0% 0% / 0.075),
      0 4px 4px hsl(0deg 0% 0% / 0.075),
      0 8px 8px hsl(0deg 0% 0% / 0.075),
      0 16px 16px hsl(0deg 0% 0% / 0.075)
    ;
  }
```

## 그림자 색의 채도 조정

* hsl() 활용
  * Hue
  * Saturation
  * Lightness
  * alpha

```html
<style>
  body {
    background-color:
      hsl(220deg 100% 80%);
  }
  
  .black.box {
    --shadow-color: hsl(0deg 0% 0% / 0.25);
  }
  .darker.box {
    --shadow-color: hsl(220deg 100% 55%);
  }
  .box {
    filter: drop-shadow(
      1px 2px 8px var(--shadow-color)
    );
  }

  .wrapper {
  display: flex;
  gap: 32px;
  }

  .box {
    width: 100px;
    height: 100px;
    border-radius: 8px;
    background: white;
  }
</style>

<section class="wrapper">
  <div class="black box"></div>
  <div class="darker box"></div>
</section>
```

## REF

[https://www.w3schools.com/css/css\_colors\_hsl.asp](https://www.w3schools.com/css/css\_colors\_hsl.asp)

[https://developer.mozilla.org/en-US/docs/Web/CSS/color\_value/hsl](https://developer.mozilla.org/en-US/docs/Web/CSS/color\_value/hsl)

## filter: drop-shadow 속성과 box-shadow의 차이

drop-shadow는 투명한 부분에는 적용되지 않는다.

box-shadow는 box의 형태로 나타난다

#### Generater로 만들어본 값

```css
:root {
  --shadow-color: 0deg 41% 51%;
  --shadow-elevation-low:
    0.1px 0.1px 0.2px hsl(var(--shadow-color) / 0.33),
    0.1px 0.2px 0.2px -1.4px hsl(var(--shadow-color) / 0.3),
    0.2px 0.5px 0.6px -2.8px hsl(var(--shadow-color) / 0.28);
  --shadow-elevation-medium:
    0.1px 0.1px 0.2px hsl(var(--shadow-color) / 0.34),
    0.2px 0.4px 0.5px -0.9px hsl(var(--shadow-color) / 0.32),
    0.5px 1px 1.2px -1.9px hsl(var(--shadow-color) / 0.31),
    1.2px 2.5px 3px -2.8px hsl(var(--shadow-color) / 0.29);
  --shadow-elevation-high:
    0.1px 0.1px 0.2px hsl(var(--shadow-color) / 0.36),
    0.3px 0.7px 0.8px -0.5px hsl(var(--shadow-color) / 0.35),
    0.6px 1.4px 1.6px -0.9px hsl(var(--shadow-color) / 0.34),
    1.2px 2.4px 2.9px -1.4px hsl(var(--shadow-color) / 0.33),
    2px 4.3px 5.1px -1.9px hsl(var(--shadow-color) / 0.32),
    3.4px 7.1px 8.5px -2.3px hsl(var(--shadow-color) / 0.31),
    5.4px 11.3px 13.5px -2.8px hsl(var(--shadow-color) / 0.3);
}
```

## REF

[https://frontdev.tistory.com/entry/CSS%EB%A1%9C-%EB%B3%B4%EB%8B%A4-%EC%95%84%EB%A6%84%EB%8B%A4%EC%9A%B4-Shadow-%EB%A7%8C%EB%93%A4%EA%B8%B0filter-box-shadow-vs-drop-shadow](https://frontdev.tistory.com/entry/CSS%EB%A1%9C-%EB%B3%B4%EB%8B%A4-%EC%95%84%EB%A6%84%EB%8B%A4%EC%9A%B4-Shadow-%EB%A7%8C%EB%93%A4%EA%B8%B0filter-box-shadow-vs-drop-shadow)

[https://www.joshwcomeau.com/css/designing-shadows/](https://www.joshwcomeau.com/css/designing-shadows/)
