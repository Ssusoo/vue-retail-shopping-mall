<!--
	11th, Input(v-model)

	복습 메뉴얼
		1) 메뉴 만들기(v-for)
		2) Json 데이터 데이터바인딩하기
		3) 모달창 만들기
		4) 클릭이벤트(신고수)
		5) 모달창 디테일(클릭했을 때)
		6) 컴포넌트1(할인팝업)
		7) 컴포넌트2(3) 모달창 만들기)
		8) 컴포넌트3(2) Json 데이터 데이터바인딩하기)
		9) 커스텀 이벤트 문법(오류난 모달창 해결하기)
-->
<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<InputModalWindowComponent
			:room="rooms"
			:open-modal-window="openModalWindow"
			:user-click-event="userClickEvent"
			@closedModal="openModalWindow = false"
	/>

	<InputDataBindingComponent
			:room="rooms[i]"
			v-for="(room,i) in rooms"
			:key="room"
			@openModal="openModalWindow = true; userClickEvent = $event"
	/>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'
import InputDataBindingComponent from '@/_11/InputDataBindingComponent'
import InputModalWindowComponent from '@/_11/InputModalWindowComponent'

export default {
	name: 'InputData',
	components: {
		InputDataBindingComponent,
		InputModalWindowComponent,
	},
	data() {
		return {
			userClickEvent: 0,
			openModalWindow: false,
			menus: ['Home', 'Product', 'About'],
			rooms: Data,
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
	background-color: rgba(0, 0, 0, 0.5);
	position: fixed;
	width: 100%;
	height: 100%;
}

.white-bg {
	background-color: white;
	width: 100%;
	border-radius: 10px;
	padding: 15px;
}

.room-img {
	margin-top: 10px;
	width: 100%;
	height: 100%;
}

.menu {
	background-color: burlywood;
	padding: 20px;
	text-align: left;
}

.menu a {
	color: black;
	padding: 15px;
	border-radius: 5px;
}
</style>