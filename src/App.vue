<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <!-- HTML 속성을 데이터 바인딩하고 싶으면 앞에 세미콜론(:) -->
    <h4 :style="color">xx 원룸</h4>
    <p>{{ dataBinding }} 만원</p>
  </div>
</template>

<script>
/* TODO 생자 자바스크립트로 하는 데이터 바인딩
  document.getElementById().innerHTML ??
*/

export default {
  name: 'App',
  // TODO 데이터 보관함.
  //  데이터는 object 자료로 저장해두기 {자료이름 : 자료내용}
  data() {
    return {
      // 데이터 데이터 바인딩
      dataBinding : 60,
      // HTML 속성 데이터 바인딩
      color: 'color: red',
    }
  },
  components: {}
}
</script>

<style></style>
