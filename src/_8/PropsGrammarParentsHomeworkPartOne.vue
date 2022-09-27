<!--
	8th, 프록스(props) 문법 숙제 Part1(할인 팝업창과 모달창을 컴포넌트로 바꾸기)

	복습 메뉴얼
		1) 메뉴 만들기(v-for)
		2) Json 데이터 데이터바인딩하기
		3) 모달창 만들기
		4) 클릭이벤트(신고수)
		5) 모달창 디테일(클릭했을 때)
		TODO 6) 컴포넌트1(할인팝업)
		TODO 7) 컴포넌트2(3) 모달창 만들기)
-->
<template>
	<!-- TODO 7) 컴포넌트2(3) 모달창 만들기) -->
	<PropsGrammarChildrenHomework
		:openModalWindow="openModalWindow"
		:rooms="rooms"
		:userClickEvent="userClickEvent"
	/>
	<!-- 1) 메뉴 만들기(v-for) -->
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>
	<!-- 2) Json 데이터 데이터바인딩하기 -->
	<div v-for="(room, i) in rooms" :key="i">
		<img :src="room.image" class="room-img">
		<!-- 3) 팝업창 만들기 & 5) 팝업창 디테일(클릭했을 때) -->
		<h4 @click="openModalWindow = true; userClickEvent = [i]">{{ room.title}}</h4>
		<p>{{ room.price}}원</p>
		<!-- 4) 클릭이벤트(신고수) -->
		<button @click="eventHandlerCount[i]+=1">허위매물신고</button> <span>신고수 : {{eventHandlerCount[i]}}</span>
	</div>
</template>

<script>
// 2) Json 데이터 데이터바인딩하기
import Data from '@/assets/jsons/oneRoom'
import PropsGrammarChildrenHomework from '@/_8/PropsGrammarChildrenHomework'

export default {
	name: 'PropsGrammarDataBindingHomeworkPartTwo',
	components: {
		PropsGrammarChildrenHomework,
	},
	data() {
		return {
			// 5) 모달창 디테일(클릭했을 때)
			userClickEvent: 0,
			// 4) 클릭이벤트(신고수)
			eventHandlerCount: [0,0,0,0,0,0,0,0,0],
			// 3) 모달창 만들기
			openModalWindow: 0,
			menus: ['Home', 'Product', 'About'],
			rooms: Data,
		}
	},
	methods: {
		increase() {
			this.eventHandlerCount += 1;
		}
	},
}
</script>

<style>
body {
	margin: 0px;
}
div {
	box-sizing: border-box;
	text-align: center;
}
.black-bg {
	background-color: rgba(0,0,0,0.5);
	position: fixed;
	width: 100%;
	height: 100%;
}
.white-bg {
	background-color: white;
	width: 100%;
	padding: 20px;
	border-radius: 5px;
}
.discount {
	background-color: darkgreen;
	padding: 20px;
	margin-bottom: 10px;
	border-radius: 5px;
}
.menu {
	background-color: sandybrown;
	padding: 20px;
	border-radius: 5px;
	text-align: left;
}
.menu a {
	padding: 15px;
	color: black;
}
.room-img {
	margin-top: 15px;
	width: 100%;
	height: 100%;
}
</style>