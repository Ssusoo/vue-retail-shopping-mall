<template>
  <!-- modal -->
  <div class="black-bg" v-if="openModal == true">
    <div class="white-bg">
      <img :src="importData[userClickData].image">
      <h4>{{importData[userClickData].title}}</h4>
      <p>{{importData[userClickData].content}}</p>
      <button @click="openModal=false">닫기</button>
    </div>
  </div>
  <!-- 상단 메뉴 -->
  <div class="menu">
    <a v-for="menuCustom in Menus" :key="menuCustom">{{ menuCustom }}</a>
  </div>

  <!-- import data -->
  <div v-for="(dataCustom, i) in importData" :key="i">
    <img class="room-img" :src="dataCustom.image">
    <h4 @click="openModal=true; userClickData = i">{{dataCustom.title}}</h4>
    <p>{{dataCustom.price}}원</p>
  </div>

	<Discount/>

</template>

<script>

// 데이터 받아오기 import {roomData1, roomData2}
// export default일 경우 알아서 import 작명 맘대로
import roomData from './assets/oneRoom'
import Discount from './components/Discount'

export default {
  name: 'App',
  // 데이터 저장소
  data() {
    return {
      Products: ['삼성동', '인사동', "천호동"],
      Menus: ['Home', "Products", "About"],
      ReportCount: [0, 0, 0],
      openModal: false,
      // import data 가져옴
      importData: roomData,
      // 사용자가 누른 버튼 기록
      userClickData: 0,
    }
  },
  // Function 저장소
  methods: {
    // function(){} 라고 생각하자.
    setReportCount() {
      this.ReportCount += 1; // 'ReportCount' is not defined(this로 해결)
    },
  },
	components: {
		Discount,
	}
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