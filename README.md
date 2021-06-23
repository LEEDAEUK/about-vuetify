# vuetify에 관하여
###

## Font

+ ### **기본폰트 변경**

    **기본 폰트를 변경할 수 있지만 약간 복잡하다. 하지만 한번 설정해두면 계속 사용할 수 있다**

1. 아래의 경로에 variables.scss 생성   
frongend / src / styles / variables.scss 


2. 아래 코드 작성   
   언어에 따라 다르게 설정 가능, 미리 설정해두면 설정해 둔 클래스로 가져다 
```css
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;500&family=Poppins:wght@300;500&display=swap");
$font-family-en: "Poppins", sans-serif;
$font-family-jp: "Noto Sans JP", sans-serif;
.my-application {
  [class*="en-weight-1"] {
    color: black;
    font-family: $font-family-en !important;
    font-weight: 500;
  }
  [class*="en-weight-2"] {
    color: black;
    font-family: $font-family-en !important;
    font-weight: 300;
  }
  [class*="jp-weight-1"] {
    color: black;
    font-family: $font-family-jp !important;
    font-weight: 500;
  }
  [class*="jp-weight-2"] {
    color: black;
    font-family: $font-family-jp !important;
    font-weight: 300;
  }
	color: black;
	font-weight: 300;
  font-family: $font-family-en !important;
}
```

3. frontend / public / index.html 에 아래 코드 추가   
```html
<link rel="preconnect" href="https://fonts.gstatic.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300;500&family=Poppins:wght@300;500&display=swap" rel="stylesheet">
```

4. 뷰티파이 기본 프로퍼티와 겹치지 않게 하기 위해 따로 클래스 지정   
```html
<v-app class="my-application">
```

5. 각 vue component에서 사용할 때 variables.scss에서 지정한 클래스로 적용 가능하다   
```html
<template>
  <v-container fill-height grid-list-xs>
    <v-layout column>
      <v-flex class="d-flex flex-column align-center justify-center">
        <v-btn @click="getUser"> get user </v-btn>
        <div class="en-weight-1 display-1">{{ user_info }}</div>

        <div class="en-weight-1 title">Almost before we knew it, we had left the ground.</div>
        <div class="en-weight-2 body-1">Almost before we knew it, we had left the ground.</div>

        <div class="jp-weight-1 title">彼らの機器や装置はすべて生命体だ。</div>
        <div class="jp-weight-2 body-1">彼らの機器や装置はすべて生命体だ。</div>
      </v-flex>
    </v-layout>
  </v-container>
</template>
```



