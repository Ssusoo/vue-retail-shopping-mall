<template>
  <!-- modal -->
  <!-- 2) 데이터에 따라 UI가 어떻게 보일지 작성 -->
  <div class="black-bg" v-if="openModal == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지-내용</p>
      <button @click="openModal=false">닫기</button>
    </div>
  </div>
  <!-- v-for 상단 메뉴 커스텀-1 -->
  <div class="menu">
    <a v-for="menuCustom in Menus" :key="menuCustom">{{ menuCustom }}</a>
  </div>
  <!-- -->
  <div>
    <img class="room-img" src="./assets/room0.jpg">
    <h4 @click="openModal=true">{{ Products[0] }}</h4>
    <p>60 만원</p>
    <!-- v-on:click="자바스크립트" === @click="자바스크립트" -->
    <button @click="ReportCount[0] += 1">허위매물신고</button>
    <span>신고수: {{ ReportCount[0] }}</span>
  </div>
  <div>
    <img class="room-img" src="./assets/room1.jpg">
    <h4>{{ Products[1] }}</h4>
    <p>70 만원</p>
    <button @click="ReportCount[1] += 1">허위매물신고</button>
    <span>신고수: {{ ReportCount[1] }}</span>
  </div>
  <div>
    <img class="room-img" src="./assets/room2.jpg">
    <h4>{{ Products[2] }}</h4>
    <p>80 만원</p>
    <button @click="ReportCount[2] += 1">허위매물신고</button>
    <span>신고수: {{ ReportCount[2] }}</span>
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
      ReportCount: [0, 0, 0],
      /*동적인 UI 만들기
          1) UI 현재 상태를 데이터 저장소에 저장
          2) 데이터에 따라 UI가 어떻게 보일지 작성
      */
      // 1) 모달창이 지금 어떻게 보여야함?(열렸니? 닫혔니?(false)
      openModal: false,
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

.room-img {
  width: 50%;
  margin-top: 40px; /*위의 간격을 넓히기*/
}

/*모달창 기초공사*/
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5); /*검은색 조그만한 박스가 만들어짐*/
  position: fixed; /*엄청 큰 검은색 박스로 변함*/
  padding: 20px;
}
.white-bg {
  width: 100%; background: white; /*검은색 박스안에 조그만한 흰색 박스*/
  border-radius: 8px; /*모서리 깍기*/
  padding: 20px;
}
</style>
