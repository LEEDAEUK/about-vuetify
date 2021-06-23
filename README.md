# 작성법

## 기본 component 작성법


```vue
<template>
  <v-container>
    <v-layout column>
      <v-flex class="d-flex align-center justify-center">
        <div></div>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  created() {
    this.$emit("Title", "title name");
  },
  data() {
    return {};
  },
  methods: {},
};
</script>

<style scoped>
</style>
```


# Font

## **기본폰트 변경**

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
 
***

## **폰트 디자인**
**class 에 작성하자: 이미 css에 적용되어 있는 폰트사이즈와 폰트 웨이트를 가져와서 사용한다고 생각하면 쉽다**

예)
```html
<p> class="title font-weight-regular"</p>
```

* ### Font size

```css
.display-1
.display-2
.display-3
.display-4
.headline
.title
.subtitle-1
.subtitle-2
.body-1
.body-2
.caption
.overline
```

* ### Font weight

```css
.font-weight-black
.font-weight-bold
.font-weight-medium
.font-weight-regular
.font-weight-light
.font-weight-thin
.font-italic
```

***

## **deep selector 작성법**
**뷰티파이의 경우, 이미 세팅된 설정을 사용하므로 자동으로 생성되는 자식 프로퍼티가 있다. 코드에 없지만 인스펙터에서 확인 가능한 프로퍼티를 만지고 싶을 때**

```css
<style scoped>
>>> .v-toolbar__content {
  padding: 0px !important;
  display: flex;
  flex-direction: column;
}
>>> .v-main__wrap {
  background-image: url("~@/assets/newspaper.jpg");
  background-size: 300px 300px;
  background-repeat: repeat;
}
>>> .v-main {
  height: 100%;
}
</style>
```

***


