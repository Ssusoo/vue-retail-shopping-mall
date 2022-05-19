<template>
  <!-- v-for 상단 메뉴 커스텀-1 -->
  <div class="menu">
    <a v-for="menuCustom in Menus" :key="menuCustom">{{menuCustom}}</a>
  </div>

  <!-- v-for 데이터 커스텀-2 -->
  <div v-for="(menuCustom, i) in Products" :key="i">
    <!-- 첫 번째 방법 -->
    <h4>{{Products[i]}} 원룸</h4>
    <!-- 두 번째 방법-->
    <h4>{{menuCustom}}</h4>
    <p>60 만원</p>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      // Data 데이터 바인딩
      Products: ['삼성동', '인사동', "천호동"],
      Menus: ['Home', "Products", "About"],
    }
  },
}
</script>

<style>
#app {
  text-align: center;
}
.menu {
  background-color: aquamarine;
  padding: 15px;
  border-radius: 5px; /*네모박스 모서리 깍기*/
}
.menu a {
  color: red;
  padding: 10px; /*Menu/Home/About 사이 간격 넓히기*/
}
</style>
