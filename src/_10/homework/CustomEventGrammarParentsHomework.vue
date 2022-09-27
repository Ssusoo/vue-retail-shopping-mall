<!--
	10th, 커스텀 이벤트 문법(오류난 모달창 닫기 버튼 해결하기)

	복습 메뉴얼
		1) 메뉴 만들기(v-for)
		2) Json 데이터 데이터바인딩하기
		3) 모달창 만들기
		4) 클릭이벤트(신고수)
		5) 모달창 디테일(클릭했을 때)
		6) 컴포넌트1 [
			할인팝업
		]
		7) 컴포넌트2 [
			3) 모달창 만들기
		]
		8) 컴포넌트3 [
			2) Json 데이터 데이터바인딩하기
		]
		9) 커스텀이벤트 [
			5) 모달창 디테일(클릭했을 때)
			6) 컴포넌트1(할인팝업)
			7) 컴포넌트2(3) 모달창 만들기)
			8) 컴포넌트3(2) Json 데이터 데이터바인딩하기)
		]
		TODO 10) 커스텀이벤트(모달창 닫기 버튼 처리하기)
-->

<template>
	<div class="menu">
		<a v-for="menu in menus" :key="menu">{{ menu }}</a>
	</div>
	<CustomEventGrammarModalWindowComponentHomework
		:open-modal-window="openModalWindow"
		:room="rooms"
		:user-click-event="userClickEvent"
		@closeModal="openModalWindow = false"
	/>

	<CustomEventGrammarDataBindingHomework
		:room="rooms[i]"
		v-for="(room, i) in rooms"
		:key="room"
		@openModal="openModalWindow = true; userClickEvent = $event"
	/>

</template>

<script>
import Data from '@/assets/jsons/oneRoom'
import CustomEventGrammarDataBindingHomework from '@/_10/homework/CustomEventGrammarDataBindingHomework'
import CustomEventGrammarModalWindowComponentHomework from '@/_10/homework/CustomEventGrammarModalWindowComponentHomework'

export default {
	name: 'CustomEventGrammarParentsHomework',
	components: {
		CustomEventGrammarDataBindingHomework,
		CustomEventGrammarModalWindowComponentHomework,
	},
	data() {
		return {
			userClickEvent: 0,
			rooms: Data,
			menus: ['Home', 'Product', 'About'],
			openModalWindow: false,
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
	border-radius: 5px;
	padding: 20px;
	background-color: white;
	width: 100%;
}
.room-img {
	margin-top: 10px;
	width: 100%;
	height: 100%;
}
.menu {
	background-color: burlywood;
	padding: 15px;
	text-align: left;
}
.menu a {
	color: black;
	padding: 10px;
}
</style>