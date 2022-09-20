<!--
	6th, 모달창 내에 상세페이지 만들기
		모달창 각각의 title을 누르면 각각의 상세페이지가 나올 수 있게 바꾸기
			TODO 사용자가 누른 상품번호로 처리해보면 어떨까?

		TODO 동적인 UI 만드는 법
		1) UI 상태를 저장해둘 데이터 만들기
		2) 데이터에 따라 HTML 어떻게 보일지
		3) UI 조작하는 버튼 만들기
-->
<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<!-- TODO 2) 데이터에 따라 HTML 어떻게 보일지(사용자가 누른 상품번호) -->
			<h4>상품번호 : {{ rooms[userClickEvent].id}}번</h4>
			<button @click="openModalWindow = false">닫기</button>
		</div>
	</div>
	<div class="menu">
		<a v-for="(menu,i) in menus" :key="i">{{ menu }}</a>
	</div>

	<div v-for="(room, i) in rooms" :key="i">
		<img class="room-img" :src="room.image">
		<!-- TODO 3) UI 조작하는 버튼 만들기(사용자가 누른 상품번호)
					* TODO @click에 1개이상 넣을 때 세미콜론 넣기 @click="1; 2"
		-->
		<h4 @click="openModalWindow = true; userClickEvent = i">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
</template>

<script>
import data from '@/assets/jsons/oneRoom'

export default {
	name: 'ModalWindowIntoDetailDataBinding',
	data() {
		return {
			// TODO 1) 사용자가 누른 모달창 처리하기(UI 상태를 저장해둘 데이터 만들기)
			userClickEvent: 0,
			openModalWindow: false,
			rooms: data,
			menus: ['Home', 'Product', 'About'],
		}
	},
}
</script>

<style>
body {
	margin: 0;
}
div {
	box-sizing: border-box;
	text-align: center;
}
.black-bg {
	width: 100%;
	height: 100%;
	padding: 20px;
	position: fixed;
	background-color: rgba(0,0,0,0.5);
}
.white-bg {
	background-color: white;
	width: 100%;
	border-radius: 5px;
	padding: 15px;
}

.room-img {
	margin-top: 10px;
	width: 100%;
	height: 100%;
}
.menu {
	text-align: left;
	background-color: sandybrown;
	padding: 15px;
	border-radius: 5px;
}
.menu a {
	padding: 10px;
	color: black;
}
</style>