<template>
  <!-- v-for 상단 메뉴 커스텀-1 -->
  <div class="menu">
    <a v-for="menuCustom in Menus" :key="menuCustom">{{ menuCustom }}</a>
  </div>


  <div>
    <h4>{{ Products[0] }}</h4>
    <p>60 만원</p>
    <!-- v-on:click="자바스크립트" === @click="자바스크립트" -->
    <button @click="setReportCount">허위매물신고</button>
    <span>신고수: {{ ReportCount }}</span>
  </div>
  <div>
    <h4>{{ Products[1] }}</h4>
    <p>70 만원</p>
  </div>
  <div>
    <h4>{{ Products[2] }}</h4>
    <p>80 만원</p>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      Products: ['삼성동', '인사동', "천호동"],
      Menus: ['Home', "Products", "About"],
      // 신고수: 0
      ReportCount: 0,
    }
  },
/* 자바스크립트에서 함수를 쓰는 이유?
  ReportCount += 1라는 긴 단어를 축약하고 싶을 때
*/
  // Function 저장소
  methods: {
    // function(){} 라고 생각하자.
    setReportCount() {
      this.ReportCount += 1; // 'ReportCount' is not defined(this로 해결)
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
