<!--
	4th, 모달창
		1) vue에서 모달창 UI 만들기
		2) vue 모달창 CSS 스타일 입히기

		* TODO vue-router 설치하면 다른 페이지도 만드는 것도 가능함(다음에 하기로)

		* TODO 동적인 UI 만드는 법
		0. HTML CSS로 디자인하기(기본)
		1. UI의 현재 상태를 데이터로 저장해둠.
		2. 데이터에 따라 UI가 어떻게 보일지 작성

		* TODO 뷰와 리액트 Tip
		data(){} 이 부분을 리액트 이런 곳에선 state라고 부릅니다.
		뭔가 정보 저장하는 곳이기도 하고
		UI의 현재 상태를 저장하는 곳이기도 하니까요.
		상태는 영어로 state입니다.
-->
<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>
	<!-- TODO 1) 모달창 UI 만들기-->
	<!-- TODO 4) 모달창 조건문으로(true일 때 열리기)-->
	<div class="black-bg" v-if="openModalWindow == true">
		<div class="white-bg">
			<h4>상세페이지임</h4>
			<p>상세페이지 내용임</p>
		</div>
	</div>

	<div>
		<img :src="require(`@/assets/images/room0.jpg`)" class="room-img">
		<!-- TODO 5) 모달창 열기-->
		<h4 @click="openModalWindow = true">{{ products[0] }}</h4>
		<p>50만원</p>
		<button @click="openEventHandlerCount[0]+=1">허위매물신고</button> <span>{{ openEventHandlerCount[0] }}</span>
	</div>
	<div>
		<img :src="require(`@/assets/images/room1.jpg`)" class="room-img">
		<h4>{{ products[1] }}</h4>
		<p>50만원</p>
		<button @click="openEventHandlerCount[1]+=1">허위매물신고</button> <span>{{ openEventHandlerCount[1] }}</span>
	</div>
	<div>
		<img :src="require(`@/assets/images/room2.jpg`)" class="room-img">
		<h4>{{ products[2] }}</h4>
		<p>50만원</p>
		<button @click="openEventHandlerCount[2]+=1">허위매물신고</button> <span> 신고수 : {{ openEventHandlerCount[2] }}</span>
	</div>
</template>

<script>
export default {
	name: 'ModalWindow',
	data() {
		return {
			// TODO 3) 모달창의 상태 저장하기
			openModalWindow: false,
			openEventHandlerCount: [0, 0, 0],
			menus: ['Home', 'Product', 'About'],
			products: ['신림동원룸', '구로동원룸', '역삼동원룸']
		}
	},
	methods: {
		increase() {
			this.openEventHandlerCount++;
		}
	}
}
</script>

<style>
/* TODO 2) vue 모달창 CSS 스타일 입히기(body, div, black-bg, white-bg */
body {
	margin: 0px;
}
div {
	box-sizing: border-box;
	text-align: center; /* Quirks Mode 를 위한 가운데 정렬 */
}
.black-bg {
	width: 100%;
	height: 100%;
	background-color: rgba(0,0,0,0.5);
	position: fixed;
	padding: 20px;
}
.white-bg {
	background-color: white;
	width: 100%;
	padding: 20px;
	border-radius: 5px;
}
/* src room 이미지 지정*/
.room-img {
	margin-top: 25px;
	width: 100%;
}

.menu {
	background-color: burlywood;
	padding: 15px;
	border-radius: 5px;
	text-align: left;
}
.menu a {
	color: black;
	padding: 10px;
}
</style>