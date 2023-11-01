##### 🍑  Front_End 과정 1단계 

## color-schema

The color-scheme CSS property allows an element to indicate which color schemes it can comfortably be rendered in.

Common choices for operating system color schemes are "light" and "dark", or "day mode" and "night mode". When a user selects one of these color schemes, the operating system makes adjustments to the user interface. This includes form controls, scrollbars, and the used values of CSS system colors.
운영 체제 색상 체계에 대한 일반적인 선택은 "light" 및 "dark" 또는 "day mode" 및 "night mode"입니다. 사용자가 이러한 색상 체계 중 하나를 선택하면 운영 체제는 사용자 인터페이스를 조정합니다. 여기에는 폼 컨트롤, 스크롤 바 및 CSS 시스템 색상의 사용된 값이 포함됩니다.


## 윈도우 > 설정 (개인설정) > 색 > "기본 앱 모드 선택"
여기에서 밝게 / 어둡게를 바꾸면 색상이 변경된다

```html
body { background:beige;}

@media (prefers-color-scheme: dark) {
  body { background: navy }
}

```
